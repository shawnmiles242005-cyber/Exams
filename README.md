package vu.comparison;

public class NARO {
   

public class NARORainfallAnalysis {
    
    public static void main(String[] args) {
        System.out.println("=== NARO Rainfall Analysis System ===");
        System.out.println("Analyzing rainfall data for Namulonge demonstration farm\n");
        
        // (i) Generate 30 random daily rainfall readings between 0 and 60 mm
        double[] dailyRainfall = generateRainfallData(30);
        
        // Display daily readings
        System.out.println("Daily Rainfall Readings (mm):");
        for (int day = 0; day < dailyRainfall.length; day++) {
            System.out.printf("Day %2d: %.2f mm\n", (day + 1), dailyRainfall[day]);
        }
        
        // (ii) Compute total and average monthly rainfall
        double totalRainfall = calculateTotal(dailyRainfall);
        double averageRainfall = totalRainfall / dailyRainfall.length;
        
        System.out.println("\n=== Monthly Summary ===");
        System.out.printf("Total Rainfall: %.2f mm\n", totalRainfall);
        System.out.printf("Average Daily Rainfall: %.2f mm\n", averageRainfall);
        
        // (iii) Count "wet days" (rainfall > 30 mm)
        int wetDays = countWetDays(dailyRainfall, 30.0);
        System.out.println("Number of Wet Days (>30 mm): " + wetDays);
        
        // (iv) Classify the month using if-else-if structure
        String classification = classifyMonth(totalRainfall);
        System.out.println("Month Classification: " + classification);
        
        // Additional analysis
        System.out.println("\n=== Detailed Analysis ===");
        System.out.printf("Maximum Daily Rainfall: %.2f mm\n", findMax(dailyRainfall));
        System.out.printf("Minimum Daily Rainfall: %.2f mm\n", findMin(dailyRainfall));
        System.out.println("Days with Zero Rainfall: " + countZeroRainDays(dailyRainfall));
    }
    
    // (i) Generate random rainfall data
    public static double[] generateRainfallData(int days) {
        
        double[] rainfall = new double[days];
        
        for (int i = 0; i < days; i++) {
            // Generate random value between 0 and 60 mm (inclusive)
            
        }
        return rainfall;
    }
    
    // (ii) Calculate total rainfall
    public static double calculateTotal(double[] rainfall) {
        double total = 0.0;
        for (double value : rainfall) {
            total += value;
        }
        return total;
    }
    
    // (iii) Count wet days
    public static int countWetDays(double[] rainfall, double threshold) {
        int count = 0;
        for (double value : rainfall) {
            if (value > threshold) {
                count++;
            }
        }
        return count;
    }
    
    // (iv) Classify month
    public static String classifyMonth(double totalRainfall) {
        if (totalRainfall <= 300) {
            return "DRY (Total ≤ 300 mm)";
        } else if (totalRainfall > 300 && totalRainfall < 600) {
            return "NORMAL (300 - 600 mm)";
        } else {
            return "FLOOD-RISK (Total ≥ 600 mm)";
        }
    }
    
    // Additional helper methods
    public static double findMax(double[] rainfall) {
        double max = rainfall[0];
        for (double value : rainfall) {
            if (value > max) {
                max = value;
            }
        }
        return max;
    }
    
    public static double findMin(double[] rainfall) {
        double min = rainfall[0];
        for (double value : rainfall) {
            if (value < min) {
                min = value;
            }
        }
        return min;
    }
    
    public static int countZeroRainDays(double[] rainfall) {
        int count = 0;
        for (double value : rainfall) {
            if (value == 0) {
                count++;
            }
        }
        return count;
    }
}
}

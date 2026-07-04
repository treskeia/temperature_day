import java.util.*;
class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("_".repeat(70));
        System.out.print("How many days? ");
        int n = sc.nextInt();
          System.out.println("_".repeat(70));
        double[] temps = new double[n];
        double max = Double.MIN_VALUE;
        double min = Double.MAX_VALUE;
        double sum = 0; 
        int maxDay = 0; 
        int minDay = 0;
        int ht_d = 0;
         int ml_d = 0;
         int cd_d = 0;
    
            
        for (int i = 0; i < n; i++) {
             System.out.print("What is temperature during day  " + (i + 1) + "? ");
             temps[i] = sc.nextDouble();
            max = Math.max(max, temps[i]);
            min = Math.min(min, temps[i]);
           sum+=temps[i];
         
            if (temps[i] == max) {
                maxDay = i + 1;
            }
            if (temps[i] == min) {
                minDay = i + 1;
            }
          
          if (temps[i] >= 30) {
               ht_d++;
          }
          else if (temps[i] < 10) {
              cd_d++;
          }
         else {
              ml_d++;
         }
         } 
          
          
          
        
        System.out.println("_".repeat(70));
       String list = Arrays.toString(temps).replaceAll("[\\[\\]]", "");
       list = list.replaceAll("\\.0\\b", ""); 
       System.out.println( "Temperature List: " + list);
        
        
     System.out.println("Highest: " + new java.text.DecimalFormat("0.##").format(max) + "\tDay: " +  maxDay);
      System.out.println("Lowest: " + new java.text.DecimalFormat("0.##").format(min) + "\tDay: " + minDay);
    
    double average = sum / n;
    int hot = (int) Math.round(ht_d * 100.0 / n);  
    int mild = (int) Math.round(ml_d * 100.0 / n);
    int cold = (int) Math.round(cd_d * 100.0 / n);
    
    System.out.println("_".repeat(70));
     System.out.println("Avereage Weather: " + average);
     System.out.println("_".repeat(70));
     System.out.println("Hot: " + ht_d + " (" + hot + "%)");
      System.out.println("Mild : " + ml_d + " (" + mild + "%)");
      System.out.println("Cold: " + cd_d + " (" +cold + "%)");
      System.out.println("_".repeat(70));
    }
}

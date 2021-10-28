import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.BitSet;


public class Hartals {

    /**
     * @param args
     */
public static void main(String[] args) throws IOException {
        
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String input = br.readLine();
        
        int totalNumberOfInputs = Integer.parseInt(input);
        int [] output = new int[totalNumberOfInputs];
        for (int i = 0 ; i < totalNumberOfInputs; i++)
        {
            int numberOfDaysToMonitor = Integer.parseInt(br.readLine());
            BitSet bitSet = new BitSet();
            int numberOfPoliticalParties = Integer.parseInt(br.readLine());
            int [] hartalFreq = new int [numberOfPoliticalParties];
            for(int j = 0; j < numberOfPoliticalParties; j++)
            {
                hartalFreq [j] = Integer.parseInt(br.readLine());
            }            
            for (int freq : hartalFreq)
            {
                int currentDay = freq;
                int count = 1;
                while (currentDay <= numberOfDaysToMonitor)
                {
                    count ++;
                    if(!bitSet.get(currentDay) && !(currentDay%7 ==6 || currentDay%7 == 0))
                    {
                        output[i] ++;
                        bitSet.set(currentDay);
                    }
                    currentDay = freq * count;
                }
            }
            
        }
    
            for(int out : output)
        {
            System.out.println(out);
        }
        }
}

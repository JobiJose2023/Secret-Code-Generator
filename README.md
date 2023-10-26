"# Secret-Code-Generator" 

package SecretCode;

public class SecretCodeGenerator {

    public static void main(String[] args) {
        String input = "Jobi";
        String secretCode = secretCode(input);
        System.out.println(secretCode);
    }

    private static String secretCode(String input) {
        StringBuilder sc = new StringBuilder();

        for (int i = 0; i < input.length(); i++) {
            char c = input.charAt(i);
            if (Character.isLetter(c)) {
                int number = Character.toUpperCase(c) - 'A' + 1; // Convert to upper case and calculate position
                String scs = String.format("%02d", number); // Ensure the format is "02d" for two-digit numbers
                sc.append(scs); // Append the formatted number to the result
            } else {
                System.out.println("The input contains non-letter characters!");
            }
        }
        return sc.toString(); // Return the secret code as a string
    }
}

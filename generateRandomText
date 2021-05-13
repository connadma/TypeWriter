import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintStream;
import java.util.ArrayList;
import java.util.Scanner;

public class RandomTextGenerator {

    public static void generate(int k, int length, String filename, String out) throws FileNotFoundException {
        if (k < 0 || length < 0) {
            throw new IllegalArgumentException("k or length less than 0");
        }
        String c = new Scanner(new File(filename)).useDelimiter("\\Z").next();
        if (k >= c.length()) {
            throw new IllegalArgumentException("k >= length of file");
        }
        PrintStream output = new PrintStream(new File(out));
        String s;
        int rs = (int) (Math.random() * (c.length() - k));
        s = c.substring(rs, rs + k + 1);
        output.print(s);
        for (int i = k; i <= length; i++) {
            char toAdd = find(c, s);
            output.print(toAdd);
            s = s.substring(1) + toAdd;
        }

    }

    private static char find(String c, String s) {
        ArrayList<Character> ac = new ArrayList<Character>();
        int start = -1;
        while (c.indexOf(s, start + 1) != -1) {
            start = c.indexOf(s, start + 1);
            if (start + s.length() != c.length() - 1) {
                ac.add(c.charAt(start + s.length()));
            }
        }
        if (ac.size() == 0) {
            int randStart = (int) (Math.random() * (c.length() - s.length()));
            String newStart = c.substring(randStart, randStart + s.length() + 1);
            return find(c, newStart);
        }
        int randNum = (int) (ac.size() * Math.random());
        return ac.get(randNum);
    }

    public static void main(String[] args) throws FileNotFoundException {
        Scanner scan = new Scanner(System.in);
        System.out.println("Hello. Which of these texts would you like to analyze?");
        System.out.println("1. Dracula\n2. Macbeth\n3. On The Origin Of Species\n4. The Brothers Karamazov\n5. White Fang");
        int c = scan.nextInt();
        System.out.println("What level of analysis would you like to use?");
        int k = scan.nextInt();
        System.out.println("How long would you like the output to be?");
        int l = scan.nextInt();
        if (c == 1) {
            generate(k, l, "Dracula.txt", "out.txt");
        } else if (c == 2) {
            generate(k, l, "Macbeth.txt", "out.txt");
        } else if (c == 3) {
            generate(k, l, "OnTheOriginOfSpecies.txt", "out.txt");
        } else if (c == 4) {
            generate(k, l, "TheBrothersKaramazov.txt", "out.txt");
        } else {
            generate(k, l, "WhiteFang.txt", "out.txt");
        }
    }
}
/*
SAMPLE OUTPUTS:

Hello. Which of these texts would you like to analyze?
1. Dracula
2. Macbeth
3. On The Origin Of Species
4. The Brothers Karamazov
5. White Fang
1
What level of analysis would you like to use?
10
How long would you like the output to be?
100

Process finished with exit code 0

out.txt:
 and then write all those terrible troubles—that may be—mind, I say may be—of such interest. He is so

=======================================================================================================================

Hello. Which of these texts would you like to analyze?
1. Dracula
2. Macbeth
3. On The Origin Of Species
4. The Brothers Karamazov
5. White Fang
4
What level of analysis would you like to use?
1
How long would you like the output to be?
10

Process finished with exit code 0

out.txt:
 anste. I a

 ======================================================================================================================

Hello. Which of these texts would you like to analyze?
1. Dracula
2. Macbeth
3. On The Origin Of Species
4. The Brothers Karamazov
5. White Fang
2
What level of analysis would you like to use?
12
How long would you like the output to be?
288

Process finished with exit code 0

out.txt:
 we’ll take tomorrow.
Is’t far you ride?

BANQUO.
Look, how our partner’s rapt.

MACBETH.
[_Aside._] The Prince of Cumberland: which honour must
Not unaccompanied invest him only,
But signs of nobleness, like stars, shall shine
On all deservers.—From hence to the palace gate
Mak
 */

# try
helloworld
//Nurul Fadzillah (202871)
//Q2
import java.util.Scanner;

public class FIFO {
	static Scanner sc = new Scanner(System.in);

	public static void main(String[] args) {
		int reference_string[] = new int[100];
		int i = 0;
		System.out.print("Enter Reference String:\nEnter -1 to exit:\nEnter No:");
		reference_string[i] = sc.nextInt();
		while (reference_string[i] != -1) {
			i++;
			System.out.print("Enter No:");
			reference_string[i] = sc.nextInt();
		}
		int n = 0;
		int j = 0;
		int k;
		int a[] = new int[n];
		int pf = 0;
		int ph = 0;
		int flag = 0;
		System.out.print("Enter no of frames:");
		n = sc.nextInt();
		System.out.print("\t\t\n\n----------------\n\t\t reference string ");
		i = 0;
		while (reference_string[i] != -1) {
			System.out.print("" + reference_string[i] + " ");
			i++;
		}
		System.out.print("\n\n");
		for (i = 0; i < n; i++) {
			a[i] = -1;
		}
		System.out.print("   |");
		for (i = 0; i < n; i++) {
			System.out.print(" F" + i + 1 + "");
		}
		System.out.print(" status\n");
		for (i = 0; reference_string[i] != -1; i++) {
			flag = 0;
			for (k = 0; k < n; k++) {
				if (a[k] != -1)
					System.out.print("" + a[k] + "d ");
				else
					System.out.print("   ");
				if (a[k] == reference_string[i]) {
					flag = 1;
					ph++;
				}
			}
			if (flag == 0) {
				System.out.print("PF\n");
				pf++;
				a[j] = reference_string[i];
				j = (j + 1) % n;
			} else {
				System.out.print("PH\n");
			}
		}
		System.out.print("No of page faults = " + pf + "\n");
		System.out.print("No of page hits = " + ph + "");
	}
}

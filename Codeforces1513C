
import java.util.*;

public class Codeforces1513C {
	
	public static int  mod = (int) (1e9 + 7);

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		int dp[][] = new int[10][200001];
		for(int i = 0 ; i < 10 ; i++)dp[i] = fill(i,200_001);
		int t=sc.nextInt();
		StringBuilder sb = new StringBuilder();
		for (int tt=0; tt<t; tt++) {
			int n=sc.nextInt(), steps=sc.nextInt();
			long ans=0;
			for (char c:(n+"").toCharArray())
				ans+=dp[c-'0'][steps];
			sb.append(ans%mod + "\n");
		}
		
		System.out.println(sb);
		sc.close();
	}

	private static int[] fill(int num, int j) {
		int count[] = new int[10];
		count[num]++;
		int ans[] = new int[j];
		ans[0] = 1;
		int sum = 1;
		int newcount[] =new int[10];
		for(int p = 1 ; p < j ; p++) {
			for(int i = 0 ; i < 9 ; i++)newcount[i+1] = count[i];
			newcount[0] = count[9];
			newcount[1]=add(newcount[1], count[9]);
			sum=add(sum, count[9]);
			int[] temp=count;
			count=newcount;
			newcount=temp;
			ans[p]=sum;
			
		}
		return ans;
	}
	private static int add(int a, int b) {
		if(a+b >= mod)return a+b-mod;
		return a+b;
	}

}

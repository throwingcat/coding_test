using System;

namespace BJConsoleApp
{
    internal class BJ12865
    {
        public static void Main(string[] args)
        {
            //Item Count / Capacity
            var input = Console.ReadLine().Split();
            int length = int.Parse(input[0]);
            int capacity = int.Parse(input[1]);

            int[] v = new int[length], w = new int[length];
            for (int i = 0; i < length; i++)
            {
                //Item Value / Item Weight
                input = Console.ReadLine().Split();
                w[i] = int.Parse(input[0]);
                v[i] = int.Parse(input[1]);
            }

            Console.WriteLine(Solution(v, w, capacity));
        }

        public static int Solution(int[] v, int[] w, int capacity)
        {
            int itemCount = v.Length;

            int[,] dp = new int[itemCount + 1, capacity + 1];
            for (int i = 1; i <= itemCount; i++)
            {
                // 무게 1 ~ 최대 무게까지 진행
                for (int j = 1; j <= capacity; j++)
                {
                    // 현재 선택된 아이템을 넣을 수 있음
                    if (w[i - 1] <= j)
                    {
                        //이전 아이템의 가치 vs 현재 아이템의 가치 + 잔여 무게에 담길 수 있는 이전 아이템의 가치   
                        dp[i, j] = Math.Max(dp[i - 1, j], v[i - 1] + dp[i - 1, j - w[i - 1]]);
                    }
                    // 넣을 수 없음
                    else
                    {
                        //이전 아이템의 가치를 대입
                        dp[i, j] = dp[i - 1, j];
                    }
                }
            }

            return dp[itemCount, capacity];
        }
    }
}

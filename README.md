#include <stdio.h>
#include <math.h>

int main()
{
    int N, M, i, j, k = 0;
    double a[100][100], max, S = 0;

    scanf("%d %d", &N, &M);

    for (i = 0; i < N; i++)
        for (j = 0; j < M; j++)
            scanf("%lf", &a[i][j]);

    max = a[0][0];
    for (i = 0; i < N; i++)
        for (j = 0; j < M; j++)
            if (a[i][j] > max) { max = a[i][j]; k = i; }

    for (j = 0; j < M; j++)
        S = S + sin(a[k][j]) + 1.0 / a[k][j];

    printf("Max = %lf (строка %d), S = %lf\n", max, k + 1, S);

    return 0;
}

//# shorttest_path.c//
#include<stdio.h>
int a[5][5],n,i,j;
void main()
{
    void getdata();
    void shortest();
    void display();
    printf("\nPROGRAM TO FIND SHORTEST PATH BETWEEN TWO NOEDS:");
    getdata();
    shortest();
    display();
}
void getdata()
{
    printf("\nENTER THE NUMBER OF HOST IN THE GRAPH:");
    scanf("%d",&n);
    printf("IF THERE IS NO DIRECT PATH\n");
    printf("ASSIGN THE HIGHEST DISTANCE VALUE 1000\n");
        for(i=0;i<n;i++)
        {
            a[i][j]=0;
            for(j=0;j<n;j++)
            {
                if(i!=j)
                {
                    printf("\nENTER THE DISTANCE BETWEEN (%d,%d);",i+1,j+1);
                    scanf("%d",&a[i][j]);
                    if(a[i][j]==0)
                    a[i][j]=1000;
                }
            }
        }
}
void shortest()
{
    int i,j,k;
    for(k=0;k<n;k++)
        for(i=0;i<n;i++)
            for(j=0;j<n;j++)
            {
                if(a[i][j]+a[k][j]<a[i][j])
                a[i][j]=a[i][k]+a[k][j];

            }
}

void display()
{
    int i,j;
    for(i=0;i<n;i++)
        for(j=0;j<n;j++)
            if(i!=j)
            {
                printf("\nSHORTEST PATH IS:(%d,%d)--%d\n",i+1,j+1,a[i][j]);
            }
}

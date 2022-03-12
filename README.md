#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
    srand(time(NULL));
    int times;//Define a variable for the user to input the times
    int count1 = 0;
    int frq3 = 0, frq5 = 0, frq7 = 0, frq9 = 0;
    int allsum = 0;
    printf("How many times do you want to roll the dices?\n");
    scanf("%d",&times);
    while (times < 10 || times >1000000) {
        printf("Please make sure that the range of the times is within 10 and 1000000.\n");
        printf("How many times do you want to roll the dices?\n");
        scanf("%d", &times);
    }
    while (count1 < times)
    {
        int evennumber = rand() % 3;
        int targerteven = evennumber*2+1;
        int oddnumber = rand() % 2 + 1;
        int targertodd = oddnumber*2;
        int onetimesum = targerteven + targertodd;
        switch (onetimesum)
        {
            case (3):
                frq3++;
                break;
            case (5):
                frq5++;
                break;
            case (7):
                frq7++;
                break;
            case (9):
                frq9++;
                break;
        }
        count1++;
        allsum += onetimesum;
    }
    int meanvalue  = allsum / times;
    printf("Sum   Frequency\n");
    printf(" 3       %d\n",frq3);
    printf(" 5       %d\n",frq5);
    printf(" 7       %d\n",frq7);
    printf(" 9       %d\n",frq9);
    printf("Mean value is %d.", meanvalue);
}

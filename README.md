#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
    srand(time(NULL));
    int times;//Define a variable for the user to input the times
    int count1 = 0;
    int frq3 = 0, frq5 = 0, frq7 = 0, frq9 = 0;//Define values to store the frequency
    int allsum = 0;
    printf("How many times do you want to roll the dices?\n");
    scanf("%d",&times);
    while (times < 10 || times >1000000) {//We must define the range of numbers from 10 to 1000000
        printf("Please make sure that the range of the times is within 10 and 1000000.\n");
        printf("How many times do you want to roll the dices?\n");
        scanf("%d", &times);
    }
    while (count1 < times)
    {
        int evennumber = rand() % 2 + 1;//we gain 1 and 2 from rand
        int targerteven = evennumber*2;//multiply by 2 gives 2 and 4
        int oddnumber = rand() % 3;//we gain 0, 1, 2 from rand
        int targertodd = oddnumber*2+1;//multiply by 2 and add 1 gives 1,3 and 5
        int onetimesum = targerteven + targertodd;//find the sum after rolling one time
        switch (onetimesum)
        {
            case (3):
                frq3++;//if we find there is a sum of 3, then the frequency will be added with 1.
                break;
            case (5):
                frq5++;//same as before
                break;
            case (7):
                frq7++;
                break;
            case (9):
                frq9++;
                break;
        }
        count1++;//count till the times ordered by users is finished
        allsum += onetimesum;//add all the sum up to find the mean
    }
    int meanvalue  = allsum / times;
    printf("Sum   Frequency\n");
    printf(" 3       %d\n",frq3);
    printf(" 5       %d\n",frq5);
    printf(" 7       %d\n",frq7);
    printf(" 9       %d\n",frq9);
    printf("Mean value is %d.", meanvalue);//show the users the results
}

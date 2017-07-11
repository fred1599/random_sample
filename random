#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>

#define FLAG -1

int *sample(int *population, int length, int k);
void display(int *array, int size);

int main(void)
{
    /* Test of sample function */

    /* create of 100 values */
    int values[100];

    /* initialize random seed: */
    srand (time(NULL));

    int i;
    for (i=0; i<100; i++)
        values[i] = i;

    /* display 28 unique elements between 0 et 99 */
    int *numbers = sample(values, 100, 28);
    if (numbers == NULL) return 1;

    display(numbers, 28);

    /* free allocate memory */
    free(numbers);

    return 0;
}

int *sample(int *population, int length, int k){

    /* Return a k length list of unique elements chosen from the population sequence */
    /* length is size of population array */

    if (k > length) return NULL;

    int *result = malloc(sizeof(int) * k);

    if (result == NULL)
        fprintf(stderr, "Mauvaise allocation de %d entiers dans la fonction sample", k);

    else{
        int j, index;

        for (j=0; j<k; j++){
            index = rand() % length;
            if (population[index] == FLAG)
                j--; /* for to subtract the number of element unique */
            else{
                result[j] = population[index]; /* insert new element in array */
                population[index] = FLAG; /* to avoid duplicates */
            }

        }
    }

    return result;
}

void display(int *array, int size){

    int i;
    for (i=0; i<size; i++)
        printf("%d ", array[i]);
    putchar('\n');
}

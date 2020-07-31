#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<time.h>
int main()
{
    char exit_option;
    printf("\n\nLet's get back to the old days...And play HAND CRICKET!!!\n\n");
    do
    {
    	
		int comp_score = 0, player_score = 0;
		char player_name[20];
		char option;
		int player_num, comp_num;
		printf("Please provide player name here: ");
		scanf("%[^\n]", player_name);  // input intake of %s terminates as it finds a white space that's why I have done this
		printf("\n Hello %s! To bat type 'B' or to bowl type 'W': ", player_name);  //we can also use switch cases
		scanf("%s", &option); //why %s here, %c isn't working and also option = getchar() isn't working
		if (option == 'B' || option == 'b')                 
		{
			printf("\nYou have chosen Batting\n");
			do
			{
				printf("\nType your number (1-6) here: ");
				scanf("%d", &player_num);
				srand(time(NULL));  //initialize random
				comp_num = rand() % 6 + 1;  //generate random number b/w 1 to 6
				printf("You: %d       Computer: %d \n", player_num, comp_num);
			
				if (player_num == comp_num)
				{
					printf("You are OUT!!! \n Your Total score: %d \n", player_score);
					
				}
				else
				{	
					player_score += player_num;
					printf("Your score: %d \n", player_score);
				}
			} while(player_num != comp_num);

			printf("\nNow, it's your Bowling\n");
		}

		else
		{
			printf("\nYou have chosen Bowling\n");
			do
			{
				printf("\nType your number(1-6) here: ");
				scanf("%d", &player_num);
				srand(time(NULL));  //initialize random
				comp_num = rand() % 6 + 1;  //generate random number b/w 1 to 6
				printf("You: %d       Computer: %d \n", player_num, comp_num);
			
				if (player_num == comp_num)
				{
					printf("You've got the computer!!! \n Computer's Total score: %d \n", comp_score);
					
				}
				else
				{	
					comp_score += comp_num;
					printf("Computer's score: %d \n", comp_score);
				}
			} while(player_num != comp_num);

			printf("\nNow, it's your Batting\n");
		}
		
		printf("\n To play again type 'R'\n To exit type 'X'\n");
		scanf("%s", &exit_option);
	} while (exit_option == 'R' || exit_option == 'r');

	
	//printf("Your Score: %d \n Computer's Score: %d \n", player_score, comp_score);
	//printf("You %s the match", &won);
	//printf("You %s the match", &lost);
	
	//do..while or break or if..else
}

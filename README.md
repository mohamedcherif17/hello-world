#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main ( int argc, char** argv )
{
    int nombreMystere,x=0;
    int life=0;
    int check=0;
    int level=2,continuerPartie=0;
    int max = 100;
    const int MIN = 1;

  //the loop that repeat this game
  do
  {
   life=0;
   check=0;
   //chose the level
   printf("chose the level of this game : 1 OR 2 OR 3\n");
   printf("1 : between 1 and 10\n2 : between 1 and 100\n3 : between 1 and 1000\n");
   scanf("%d",&level);

   switch(level)
    {
    case 1:
        max = 10;
        break;
    case 2:
        max = 100;
        break;
    case 3:
        max = 1000;
        break;
    default:
        printf("Level not recognized. I choose level 2 for you (between 1 and 100).\n\n");
        max = 100;
    }



   // Génération du nombre aléatoire

     srand(time(NULL));
     nombreMystere = (rand() % (max - MIN + 1)) + MIN;


   while(x != nombreMystere && check==0){

    printf("The number please ? ");
    scanf("%d", &x);
    life++;
       // we compare the input of user with the answer
    if(x>nombreMystere){
        printf("to big\n");
    }
    if(x<nombreMystere){
        printf("to small\n");
    }
    //check number of shots remains
    if(life>=3){
        check=1;
    }
    }

    //  check if the user get the number or not
   if(check==1){
    printf("you are out of shots\n");
   }else{
    printf("well done mate\n");
   }

   //Ask if the player wants to play another game!
    printf("want to replay the game: 1/0 ");
    scanf("%d",&continuerPartie);
   }while(continuerPartie==1);

return 0;
}

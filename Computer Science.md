## Directory
[Home](https://github.com/keysor/ITFinal/blob/main/README.md) | [Resume](https://github.com/keysor/ITFinal/blob/main/Resume.md) | [Major](https://github.com/keysor/ITFinal/blob/main/Major.md) | [Roll Carts](https://github.com/keysor/ITFinal/blob/main/Roll%20Carts.md) | [Ocean](https://github.com/keysor/ITFinal/blob/main/Ocean.md)

# Computer Science
In my Computer Science class we did a whole bunch of fun stuff in the language C.
* We began with Hello World
* Some arithmetic programs
* DnD programs
* A peer even coded Tetris!
```
#include <stdio.h>
#include <string.h>
#include "fight.h"

#define FILENAME "monster.csv"
int main(int argc, char * argv[])
{
    char max[256];
    char elemental[256];
    strcpy(max, "Max");
    strcpy(elemental, "Air Elemental");

    char temp_name[256], temp_at1[256], temp_at2[256], temp_extra[256];
    int temp_ac, temp_hp, temp_th;

    char m1_name[256], m1_at1[256], m1_at2[256], m1_extra[256];
    int m1_ac, m1_hp, m1_th;

    char m2_name[256], m2_at1[256], m2_at2[256], m2_extra[256];
    int m2_ac, m2_hp, m2_th;

    FILE * fp;
    char name[256];
    fp = fopen(FILENAME,"r");

    if (NULL!=fp)
    { 

        while (fp && !feof(fp))
        {
            fscanf(fp, " %[^,],%d,%d,%d,%[^,],%[^,],%s",temp_name,&temp_ac,&temp_hp,&temp_th,temp_at1,temp_at2,temp_extra);

            if (strcmp(temp_name, max) == 0) {
                strcpy(m1_name,temp_name);
                 strcpy(m1_at1,temp_at1);
                 strcpy(m1_at2,temp_at2);
                 strcpy(m1_extra,temp_extra);
                 m1_ac = temp_ac;
                 m1_hp = temp_hp;
                 m1_th = temp_th;
            }
                else if (strcmp(temp_name, elemental) == 0) {
                    strcpy(m2_name,temp_name);
                    strcpy(m2_at1,temp_at1);
                    strcpy(m2_at2,temp_at2);
                    strcpy(m2_extra,temp_extra);
                    m2_ac = temp_ac;
                    m2_hp = temp_hp;
                    m2_th = temp_th;
                }
               
            }
        }
Fight(m1_name,m1_ac,m1_hp, m1_th,m1_at1,m1_at2,m1_extra,m2_name,m2_ac, m2_hp, m2_th,m2_at1,m2_at2,m2_extra);



fclose(fp);
}
```
Heres my Code that would scan a file that was already amde that had a list of enemies with their health, name, attack stats and everything and would randomize a fight between them and print each attack and who won in the end.
Super fun to code and really wasn't that complicated! It ended really well and although I could have put switch statements in there I was happy with the results.

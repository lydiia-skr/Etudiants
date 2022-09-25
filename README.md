
//Gérer des etudiants//
#include <iostream>
#include <stdlib.h>
#include <stdio.h>
#include <conio.h>
using namespace std;
typedef struct date {
int jour,mois,annee;


};

typedef struct Etudiant {
    int matricule;
    char nom[50],prenom[50];
    date date_n;
    int nombre_inscription;
    float T1[6];
};
int Register ( Etudiant T[100], int taille )
{ int Mat=0,i=0,j=0;

 bool trouve=0;

  /* ajouter le premier etudiant */
         Mat=2022*10000+taille+1;
          T[taille].matricule=Mat;
         cout << " Entrez le nom " << endl;
         cin >> T[taille].nom;
         cout << " Entrez le prenom " << endl;
        cin >> T[taille].prenom;

        do    /* boucle repter pour le jour */
             {
             cout << " entrez le jour " << endl;
             cin >> T[taille].date_n.jour;
             }
             while ( T[taille].date_n.jour<=0 ||  T[taille].date_n.jour>31);


         do   /* boucle repter pour le mois */
             {
             cout << " entrez le mois " << endl;
              cin >> T[taille].date_n.mois;
             }
             while ( T[taille].date_n.mois<=0 ||  T[taille].date_n.mois>12);


		 cout << " entrez l'annee " << endl;   /*  L'annee  */
         cin >>T[taille].date_n.annee;



         cout << " Entrez le nombre d'inscription " << endl;
         cin >> T[taille].nombre_inscription;
         for (j=0;j<=5;j++ )
         {
             do        /* Boucle pour les modules */
             {
             cout << " entrez la note du  module " << j+1 << endl;
             cin >> T[taille].T1[j];
             }
             while ( T[taille].T1[j]<0 ||  T[taille].T1[j]>20);
         }
/* ajouter encore si la réponse est oui */
  for (i=1;i>=1;i++)
  {

      cout << " voulez-vous ajouter un etudiant ? " << " Tapez 1 pour oui et 0 pour non " << endl;
      cin >> trouve;
      if ( trouve ==1)
      {
        taille=taille+1;
         Mat=2022*10000+taille+1;
          T[taille].matricule=Mat;
         cout << " Entrez le nom " << endl;
         cin >> T[taille].nom;
         cout << " Entrez le prenom " << endl;
         cin >> T[taille].prenom;
        do    /* boucle repter pour le jour */
             {
             cout << " entrez le jour " << endl;
             cin >> T[taille].date_n.jour;
             }
             while ( T[taille].date_n.jour<=0 ||  T[taille].date_n.jour>31);

         do   /* boucle repter pour le mois */
             {
             cout << " entrez le mois " << endl;
              cin >> T[taille].date_n.mois;
             }
             while ( T[taille].date_n.mois<=0 ||  T[taille].date_n.mois>12);


		 cout << " entrez l'annee " << endl;   /*  L'annee  */
         cin >>T[taille].date_n.annee;

         cout << " Entrez le nombre d'inscription " << endl; /*  Numero d'inscription  */
         cin >> T[taille].nombre_inscription;

         for (j=0;j<=5;j++ ) /*  boucle  pour enregister les notes des modules */
         {
             do /*  boucle repter pour les notes soit pas suprieure strictement  a 20 et inferieur strictement a 0  */
             {
             cout << " entrez la note du  module " << j+1 << endl;
             cin >> T[taille].T1[j];
             }
             while ( T[taille].T1[j]<0 ||  T[taille].T1[j]>20);
         }



      }
      else /*  si la reponse est non , alors on doit casser la boucle   */
      {
          break;

      }
}
    taille=taille+1; /* Ajouter un 1 pour la prochaine utulisation de cette fonction au cas ou  */
    return (taille);
}

int Update (Etudiant T[100], int taille )
{ int N_inscription=0,i=0,j,N,M;
  cout << " Entrez le numero d'inscription " << endl;
  cin >> N_inscription;
    while ( T[i].nombre_inscription!=N_inscription && i<taille ) /* boucle tant que pour parcourrir et chercher numero d'inscription s'il existe  */
    {
        i=i+1;
    }
      if ( i>= taille ) /* Si i depasse taille alors automatqiuement Etudiant n'existe pas et la fonction reutrne 0 */
      {
        N=0;
        return (N);
      }
else  /* faire la mis a jour pour cet etudiant  */
{

         cout << " Entrez le nom " << endl;
         cin >> T[i].nom;
         cout << " Entrez le prenom " << endl;
         cin >> T[i].prenom;


        do    /* boucle repter pour le jour */
             {
             cout << " entrez le jour " << endl;
             cin >> T[i].date_n.jour;
             }
             while ( T[i].date_n.jour<=0 ||  T[i].date_n.jour>31);


         do   /* boucle repter pour le mois */
             {
             cout << " entrez le mois " << endl;
              cin >> T[i].date_n.mois;
             }
             while ( T[i].date_n.mois<=0 ||  T[i].date_n.mois>12);


		 cout << " entrez l'annee " << endl;   /*  L'annee  */
         cin >>T[i].date_n.annee;



         cout << " Entrez le nombre d'inscription " << endl;
         cin >> T[i].nombre_inscription;
         for (j=0;j<=5;j++ )
         {
             do /*  boucle repter pour les notes soit pas suprieure strictement  a 20 et inferieur strictement a 0  */
             {
             cout << " entrez la note du  module " << j+1 << endl;
             cin >> T[i].T1[j];
             }
             while ( T[i].T1[j]<0 ||  T[i].T1[j]>20);


             }
    M=1; /* la mise a jour a été effectuée avec succes , donc il renvoie 1 */

}
    return (M);
}

int Delete ( Etudiant T[100], int taille )
{ int i,mat=0,j=0;


    cout << " Entrez le matricule " << endl;  /* chercher l'etudiant par son mtricule  */
    cin >> mat;
    while (T[i].matricule!= mat &&  i<taille )
    {

    i=i+1;

	}
     if ( i>=taille)
     {
     	cout << " Etudiant inexistant "  << endl;

	 }
	 else
     {

         for ( j=i;j<taille-1;j++)
         {
             T[j]=T[j+1];
         }

         taille=taille-1;
     }


    return taille;
}
float mean(Etudiant E)
{ int i=0;
  float S=0;
  for (i=0;i<=5;i++)
  {
      S=S+E.T1[i];

  }

    S=S/6;

    return (S);
}
void Showmajor ( Etudiant T[100], int taille )
{ float A[100];
int i=0,j=0,Max=0;
char B;
for (i=0;i<taille;i++)  /* Créer un tableau et affecter les moyenne */
{
    A[i]=mean(T[i]);

}
if ( taille>0 )
{


Max=A[0]; /* le maxiumum de ce tableau sera le major de promo , */
 for ( i=1;i<=taille;i++)

 {
    if (Max < A[i])
    {
        Max=A[i];
        j=j+1; /* chercher la numero de la case de la plus grand moyenne pour afficher son nom */
    }
 }
 cout << " le major de promo est " << T[j].prenom << endl;
}
else /* si taille ne  soit pas suprieur strictement a  0 alors y'as pas des étudiants  */
{
    cout << " Y'as pas des etudiants inscris , vous devez d'abord inscrire des etudiants  !!!!! " << endl;

}

}
void showadmis ( Etudiant T[100], int taille )
{ float A[100];
   int i,j,k=0;
   if ( taille >0 )
   {
   for (i=0;i<taille;i++)
   {
       A[i]=mean(T[i]);
       if (A[i]>=10)
       {
           cout << T[i].prenom << " est admis " << endl;
           k=k+1; /* chercher combien des etudiants sont admis  */
       }
   }
  if ( k==0 )
   {
       cout << " Yas pas des etudiant admis , ils sont tous ajournee " << endl;
   }

   }
   else  /* si taille ne depasse soit pas suprieur strictement a  0 alors y'as pas des étudiants  */
   {
       cout << " Y'as pas des etudiants inscris , vous devez d'abord inscrire des etudiants  !!!!! " << endl;

   }

}
void showajourne ( Etudiant T[100], int taille )
{
 float A[100];
   int i=0,j=0,k=0;
    if ( taille >0 )
   {
   for (i=0;i<taille;i++)
   {
       A[i]=mean(T[i]);
       if (A[i]<10)
       {
           cout << T[i].prenom << " est ajourne " << endl;
           k=k+1; /* chercher combien des etudiants sont ajournee  */
       }
   }
     if ( k==0 )
   {
       cout << " Yas pas des etudiants ajournee , ils sont tous admis " << endl;
   }

   }
   else /* si taille ne soit pas suprieur strictement a  0 alors y'as pas des étudiants  */
   {
   cout << " Y'as pas des etudiants inscris , vous devez d'abord inscrire des etudiants !!!!!!!!!!! " << endl;
   }

}
void showall ( Etudiant T[100], int taille )
{ int i=0,j=0;

if ( taille>0) /* Si la taille est suprieure  strictement a  0 , donc il existe des etudiants qui sont deja inscris */
{

for (i=0;i<taille;i++) /* il doit parcourrir jusqu'a taille-1 parce que on a deja ajouter un +1 a taille */
{ cout << " Etudiant " << i+1 << ":"<<  endl;

 cout  << " " << endl;
  cout << " Nom :  " <<  T[i].nom << " |" << " prenom :  " <<  T[i].prenom << endl;
  cout << " La date de naissance  :  " << T[i].date_n.jour<<"/"<<T[i].date_n.mois<<"/"<<T[i].date_n.annee<< endl;
  cout << " Le matricule : " << T[i].matricule << " |" << " Le nombre d'inscription : " << T[i].nombre_inscription << endl;
   cout << " Les notes des modules : ";
   for (j=0;j<=5;j++)
   {
       cout << T[i].T1[j] << " " ;
   }
     cout << "  " << endl;
     cout << "  " << endl;

}

}
else
{
    cout << " Y'as pas des etudiants inscris , vous devez d'abord inscrire des etudiants  !!!! " << endl;
}
}

void showMenu() /*  Menu 	!!!!!!!!!!  */
{
    cout<<"\n\n\n\n";
    cout<<"  #####################################################\n";
    cout<<"     1.  Inscrire des Etudiants."<<endl;
    cout<<"     2.  Mettre a jour les informations d'un Etudiant. "<<endl;
    cout<<"     3.  Supprimer des Etudiants"<<endl;
    cout<<"     4.  Afficher l'Etudiant major de promotion"<<endl;
    cout<<"     5.  Afficher les Etudiants admis"<<endl;
    cout<<"     6.  Afficher les Etudiants ajournes"<<endl;
    cout<<"     7.  Afficher tous les etudiants."<<endl;
    cout<<"     8.  Quitter."<<endl;
    cout<<"  #####################################################"<<endl;
    cout<<"\t Votre choix :   "<<endl;
}
void showMenu();
int main()
{
 int taille1=0,k=0,L;
char c;
Etudiant M[100];
    do{
        showMenu();
        cin>>c;
        switch(c)
        {
        case '1':
             system("cls");
             taille1=Register(M,taille1);
             cout << " le nombre des etudiants ajoutes est " << taille1 << endl;
            getche();
            break;
        case '2':
            system("cls");
             L=Update(M,taille1);
             if ( L==1)
             {
                 cout << "  la mise a jour est effectuee avec succes " << endl;
             }
             if ( L==0)
             {
                 cout << " Etudiant inexistant " << endl;
             }
             getche();
            break;
        case '3':
            system("cls");
            taille1=Delete(M,taille1); /* récupérer la nouvelle taille   */
            getche();
            break;
        case '4':
            system("cls");
            Showmajor(M,taille1);  /* Affihcer le major de promo   */
            getche();
            break;
        case '5':
            system("cls");
            showadmis(M,taille1 ); /* afficher les étudiants admis   */
            getche();
            break;
        case '6':
            system("cls");
            showajourne(M,taille1 ); /* Afficher les étudiants ajourne   */
            getche();
            break;
        case '7':
            system("cls");
            showall(M,taille1 );  /* Afficher tout les étudiants   */
            getche();
            break;
        case '8':
            cout<<"voulez vous quitter le programme o/n ??\n"<<endl;
            cin>>c;
            break;
        }
        system("cls");
    }
    while(c!='o');
    return 0;
}

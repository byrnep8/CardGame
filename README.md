import java.util.*;
import static java.lang.System.*;

public class Library{
  //Enum to define values for each face value    
  public enum Face{
  Ace, Two, Three, Four, Five, Six, Seven, Eight, Nine, Ten, Jack, Queen, King}          
  
  //Enum to define values for each suit    
  public enum Suit{
  Clubs, Spades, Diamonds, Hearts}
  
  public Card(Suit suit, Face face){
    this.face = face;
    this.suit = suit;
  }
  
  public static void FillDeck(Card []deck)
  {
    int p=0;//Counter to fill deck        
    //For loop used to fill the deck with all the cards    
    for(int i=0; i<4; i++)    
    {      
      for(int j=0; j<13; j++)      
      {        
        deck[p].Face=i;       
        deck[p].Suit=j;        
        p++;      
      }    
    }
  }
  
  public static void Deal(Card []deck, Card []player1, Card []player2)
  {
  
    //Counter to insert Cards into 2 player decks
    int p=0;
    
    //Creating a temporary Card to hold values
    Card temp;
    
    //For Loop to insert Cards into 2 player decks
    for(int i=0; i<14; i++)
    {
      player1[p].Face = deck[0].Face;
      player1[p].Suit = deck[0].Suit;
      
      for(int j=0; j<50-i; j++)
      {
        deck[j].Face = deck[j+1].Face;
        deck[j].Suit = deck[j+1].Suit;
      }
      i++;
      
      player2[p].Face = deck[0].Face;
      player2[p].Suit = deck[0].Suit;
    }
  }
  
  public static void RemoveCard(int Index, Card []deck)
  {
    for(int i=Index; i<deck.length-1; i++)
    {
      deck[i].Face = deck[i+1].Face;
      deck[i].Suit = deck[i+1].Suit;
    }
  }
  
  public static void main(String []args)
  {
    Card []deck;
    Card []player1;
    Card []player2;
    
    FillDeck([]deck);
    
    Deal(deck[], plaqyer1[], player2[]);
    
   }
}

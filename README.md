

1. a) Write a constructor for the class Movie, which takes a String representing the title of the movie, 
// a String representing the studio, and a String representing the rating as its arguments, and sets the 
// respective class properties to these values.

class movies {
    constructor(title, studio, rating) {
      this.title = title;
      this.studio = studio;
      this.rating = rating;
    }
  
    getrating() {
      return "the movie rating is " + this.rating;
    }
  }
  
//   b)
   
  class movies {
      constructor(title, studio, rating){
          this.title = title;
          this.studio = studio;
          this.rating = "PG";
      }
  }

//   c)
  
 const CasinoRoyale = new movies( "BMW", "ROLEX", "PG13");

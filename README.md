                                                            oops tasks
1.The class Movie is stated below. An instance of class Movie represents a film. This class has the following three properties:

title, which is a String representing the title of the movie
studio, which is a String representing the studio that made the movie
rating, which is a String representing the rating of the movie (i.e. PG­13, R, etc)

a) Write a constructor for the class Movie, which takes a String representing the title of the movie, a String representing the studio, and a String representing the rating as its arguments, and sets the respective class properties to these values.

b) The constructor for the class Movie will set the class property rating to "PG" as default when no rating is provided.

c) Write a method getPG, which takes an array of base type Movie as its argument, and returns a new array of only those movies in the input array with a rating of "PG". You may assume the input array is full of Movie instances. The returned array need not be full.

d) Write a piece of code that creates an instance of the class Movie with the title “Casino Royale”, the studio “Eon Productions”, and the rating “PG­13”


 CODE:
  ------

   
class Movie                                          

{
    

       constructor(title,studio,rating="PG") 
                           
               {                                                                                                                                                                             
                   this. title=title
                   this. studio=studio
                   this. rating=rating
               }

      getPG(movie=[])                       
               {
                    movie=[this.title,this.studio,this.rating]   
                    let result=[]

                   console.log("print only films with rating PG ")
                   if(movie[2]=="PG")
                     {
                         for(var i=0;i<movie.length;i++)
                             {
                                  result=result+movie[i]+"  "
                            }
                     } 

                  return result                          
             }
  }

     let movie                                                                           
                                     
    let film=new  Movie("Casino Royale","Eon Prodductions","PG13")  

    let film1=new Movie("The Tomorrow War","Paramount pictures") 

    let film2=new Movie("AVATAR","20th Century fox")

    console.log(film.getPG(movie))          
    console.log(film1.getPG(movie))
    console.log(film2.getPG(movie))

2.Circle - Class
     Convert the UML diagram to Typescript class. - use number for double

       https://github.com/rvsp/typescript-oops/blob/master/Practice/class-circle.md

   CODE:
    -------

   class Circle
    {
          radius:number=1.0     //fields radius and color
          color:String="red"
      
       Circle(radius:number,color:String)   

           {  
          
              radius=radius 
              color=color
           
             return `${radius}  ${color}`
         }

      getRadius():number
         {
           return this.radius
        }

     setRadius(radius:number):void
       {
          if(typeof radius!='number')
           {
               throw new Error('Invalid')
           }
         else
           {
              this.radius=radius   
              console.log(radius)
            }
       }


     getColor():String
       {
         return this.color
       }


      setColor(color:String):void
       {
            if(!color)
             {
                 throw new Error('Invalid')
             }
          else
          {
             this. color=color
              console.log(color)
          }

      }


      toString():String
      {
          var radius:String
          radius=this.radius.toString()
          return `Circle [radius=${radius} , color= ${this.color}]`
      }


     getArea():number
     {
         var area:number
         area=3.14159*(this.radius*this.radius)   //area of circle=pi *squareof(radius)  pi=3.14159
         return area
     }

   getCircumference():number
     {
        let circumference:number
        circumference=2*3.14159*this.radius    //circumference of circle=2*pi*radius
        return circumference
     }
}


     var obj=new Circle()  //object creation
       
      console.log( obj.Circle(1,"blue"))  

      console.log(obj.getRadius())   

      obj.setRadius(2)           
      console.log(obj.getColor())   

      obj.setColor("green")    

      console.log(obj.toString())  

      console.log(obj.getArea())  

     console.log(obj.getCircumference())  // 12.56636


   OUTPUT:
   -----------

   [LOG]: "1  blue" 
  [LOG]: 1 
  [LOG]: 2 
  [LOG]: "red" 
  [LOG]: "green" 
  [LOG]: "Circle [radius=2 , color= green]" 
  [LOG]: 12.56636 
 [LOG]: 12.56636



  3.Write a “person” class to hold all the details.


    CODE:
     ------

  class Person
{
        constructor(Firstname,Lastname,Age,Jobdescription,City,Country,Sport)
             {
     
                   this.Firstname=Firstname
                   this.Lastname=Lastname
                   this.Age=Age
                   this.Jobdescription=Jobdescription
                   this.City=City
                   this.Country=Country
                   this.Sport=Sport

                 this.getFullName=function () 
                        {

                                    return `Full Name is  ${this.Firstname}  ${this.Lastname}`
                        }
            }

     getdetails () 
            {
       return `
           FirstName     :${this.Firstname}
           Lastname      :${this.Lastname}
           Age           :${this.Age}
           Jobdescription:${this.Jobdescription}
           City          :${this.City}
           Country       :${this.Country}
           Sport          :${this.Sport}`
          }   
   }
    

  
   let person1=new Person("Bill","Gates","60","Microsoft Founder","New York","USA","Football")

  let person2=new Person("Sunder","Pichai","40","ALphabet CEO","Chennai","India","Cricket")

     console.log(`Person 1: ${person1.getFullName()} ${person1.getdetails()}`)
      console.log(`Person 2: ${person2.getFullName()} ${person2.getdetails()}`)

    OUTPUT:
  
    Person 1: Full Name is  Bill  Gates 
           FirstName     :Bill
           Lastname      :Gates
           Age                :60
           Jobdescription:Microsoft Founder
           City               :New York
           Country        :USA
           Sport            :Football
   
   Person 2: Full Name is  Sunder  Pichai 
           FirstName     :Sunder
           Lastname       :Pichai
           Age                 :40
           Jobdescription:ALphabet CEO
           City               :Chennai
           Country       :India
           Sport           :Cricket






4.write a class to calculate uber price.

      CODE:
     
   class Uberfare
   {

            constructor(distance,time)
                               {
                                       this.distance=distance
                                       this.time=time
                                }

             getPrice(perkm_rate,base_fare,per_minute,minimum_fare)
                           {

                                 let ride_perkm=this.distance*perkm_rate   

                                 let ride_minute=(this.time*per_minute)  

                                 let result=base_fare+ride_perkm+ride_minute   
                                                                                                               
       
                                  if(result<minimum_fare)                 
                                    {
                                                 result=minimum_fare
                                     }
    
                                return `For a ${this.distance}km ride spanning ${this.time} minutes  fare is ${result} `

                               }
    

   }


      const perkm_rate=14.7,base_fare=48,per_minute=1,minimum_fare=85  
      var price=new Uberfare("10","30")          
      var price1=new Uberfare("2","3")
        

      console.log("Uber Price")    

      console.log(price.getPrice(perkm_rate,base_fare,per_minute,minimum_fare))
      console.log(price1.getPrice(perkm_rate,base_fare,per_minute,minimum_fare))

     OUTPUT:
 
  
                            
index.js:113            For a 10km ride spanning 30 minutes  fare is 225 

index.js:114            For a 2km ride spanning 3 minutes  fare is 85

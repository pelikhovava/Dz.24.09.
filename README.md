<?php
/*Здоровье человека не может быть более 100 единиц*/
  class Person{
    private $name;
    private $lastname;
    private $age;
    private $hp;
    private $mother;
    private $father;
    private $dadfather;
    private $dadmother;
    private $momfather;
    private $mommother;

    function __construct($name,$lastname,$age,$mother=null,$father=null,$dadfather=null,$dadmother=null,$momfather=null,$mommother=null){ 
      $this->name = $name;
      $this->hp = 100;
      $this->$lastname = $lastname;
      $this->age = $age;
      $this->mother = $mother;
      $this->father = $father;
      $this->dadfather = $dadfather;
      $this->dadmother = $dadmother;
      $this->momfather = $momfather;
      $this->mommother = $mommother;
    }
    function sayHi($name){
      return "Hi $name. my name is ".$this->name;
    }
    function setHp($hp){
      if ($this->hp+$hp>=100) $this->hp=100;
      else $this->hp = $this->hp+$hp;
    }
    function getHp(){return $this->hp;}
    function getName(){return $this->name;} 
    function getMother(){return $this->mother;}
    function getFather(){return $this->father;}
    function getDadfather(){return $this->dadfather;}
    function getDadmother(){return $this->dadmother;}
    function getMomfather(){return $this->momfather;}
    function getMommother(){return $this->mommother;}
    
    function getInfo(){
      return"
      My name is:".$this->getName()."<br>
      My mother is:".$this->getMother()->getName()."<br> 
      My father is:".$this->getFather()->getName()."<br>
      My dad's father is:".$this->getDadfather()->getName()."<br>
      My dad's mother is:".$this->getDadmother()->getName()."<br>
      My mom's father is:".$this->getMomfather()->getName()."<br>
      My mom's mother is:".$this->getMommother()->getName()."<br>
      ";
    }
  }
  
  $max = new Person("Max", "Petrov",65);//родители Ольги
  $vika = new Person("Vika", "Petrova",65);

  $ivan = new Person("Ivan", "Ivanov",68);//Родители Алекса
  $vera = new Person("Vera", "Ivanova",68);
  
  $alex = new Person("Alex", "Ivanov",42,$vera,$ivan); /*создали объект*/
  $olga = new Person("Olga", "Ivanova",42,$vika,$max);
  $valera = new Person("Valera", "Ivanov",17,$olga,$alex,$ivan,$vera,$max,$vika);
  echo $valera->getInfo();

?>

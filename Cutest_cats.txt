
import os

class CutestCats:
    def __init__(self):
      self.__Name = "" #this is a  String
      self.__Description = "" #this is a String
      self.__Weight = 0 #Real
      self.__Length = 0 #Real
      self.__LifeExpectancy = 0 #Real
      self.__ImageUrl = [] #Array
      self.__CatTupple = ([]) #Tuple
      self.__temp = [] #list 
      
    def Constructor(self):
      try:
        with open("CutestCats.txt","r") as t:
          i = 1
          for lines in t:
            if i == 1:
              self.__Name = (lines.strip("\n"))
              self.__temp.append(self.__Name)
            if i == 2:
              self.__Description = (lines.strip("\n"))
              self.__temp.append(self.__Description)
            if i == 3:
              self.__Weight = (lines.strip("\n"))
              self.__temp.append(self.__Weight)
            if i == 4:
              self.__Length = (lines.strip("\n"))
              self.__temp.append(self.__Length)
            if i == 5:
              self.__LifeExpectancy = (lines.strip("\n"))
              self.__temp.append(self.__LifeExpectancy)
            if i == 6:
              self.__ImageUrl = (lines.strip("\n"))
              self.__temp.append(self.__ImageUrl)
              self.__CatTupple += tuple(self.__temp)
              self.__temp = []
              
              i = 1
            i += 1
            
            
      except OSError:
        print("cant find dictionary, current dictionary is:",os.getcwd)

    def GetCatDetails(self):
      print(self.__CatTupple)
        
Object = CutestCats()
Object.Constructor()
Object.GetCatDetails()


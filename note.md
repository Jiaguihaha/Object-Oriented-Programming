note.dt

class Point: 
  def __init__(self,x,y): 
    self.x = x
    self.y = y
  def __str__(self):
    return f"Point Object ({self.x}, {self.y})" 
    
  def __repr__(self): 
    return self.__str__() 
    
  def distance(self, other_point):
    diff_x = (self.x - other_point.x)**2
    diff_y = (self.y - other_point.y)**2
    result = (diff_x + diff_y)**0.5
    return result
    
  def __mul__(slef,num): 
    return Point(self.x * num, self.y * num) 
  
 
 test1 = Point(2,6)
 test2 = Point(-1,5)
 origin = Point(0,0)

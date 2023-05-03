Download Link: https://assignmentchef.com/product/solved-cs2030s-problem-set-2-inheritance-and-polymorphism
<br>



<ol>

 <li>Study the following Point and Circle classes.</li>

</ol>

public class Point { private final double x; private final double y;

public Point(double x, double y) { this.x = x; this.y = y;

} }

public class Circle {

private final Point centre; private final int radius;

public Circle(Point centre, int radius) { this.centre = centre; this.radius = radius;

}

@Override

public boolean equals(Object obj) {

System.out.println(“equals(Object) called”); if (obj == this) { return true;

}

if (obj instanceof Circle) { Circle circle = (Circle) obj;

return (circle.centre.equals(centre) &amp;&amp; circle.radius == radius);

} else {

return false;

} }

public boolean equals(Circle circle) {

System.out.println(“equals(Circle) called”); return circle.centre.equals(centre) &amp;&amp; circle.radius == radius;

}

}

1

Given the following program fragment,

Circle c1 = new Circle(new Point(0, 0), 10);

Circle c2 = new Circle(new Point(0, 0), 10);

Object o1 = c1;

Object o2 = c2;

what is the output of the following statements?

<table width="515">

 <tbody>

  <tr>

   <td width="277">(a)     o1.equals(o2);(b)    o1.equals((Circle) o2);(c)     o1.equals(c2);(d)    o1.equals(c1);</td>

   <td width="237">(e)    c1.equals(o2);(f)      c1.equals((Circle) o2);(g)    c1.equals(c2);(h)    c1.equals(o1);</td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>We would like to design a class Square that inherits from Rectangle. A square has the constraint that the four sides are of the same length.</li>

</ol>

<ul>

 <li>How should Square be implemented to obtain the following output from JShell?</li>

</ul>

jshell&gt; new Square(5)

$3 ==&gt; area 25.00 and perimeter 20.00

<ul>

 <li>Now implement two separate methods to set the width and height of the rectangle:</li>

</ul>

public Rectangle setWidth(double width) { … } public Rectangle setHeight(double height) { … }

What undesirable design issues would this present?

<ul>

 <li>Now implement two overriding methods in the Square class</li>

</ul>

@Override

public Square setHeight(double height) { return new Square(height);

}

@Override

public Square setWidth(double width) { return new Square(width);

}

Do you think that it is now sensible for to have Square inherit from Rectangle? Or should it be the other way around? Or maybe they should not inherit from each other?

2
Download Link: https://assignmentchef.com/product/solved-cmi-assignment-4-structures-and-subroutines
<br>
Create an ARMv8 assembly language program that implements the following program:

#define FALSE  0

#define TRUE   1




struct point {

int x, y;

};




struct dimension {

int width, length;

};




struct cuboid {

struct point origin;

struct dimension base;

int height;

int volume;

};







struct cuboid newCuboid()

{

struct cuboid c;




c.origin.x = 0;

c.origin.y = 0;

c.base.width = 2;

c.base.length = 2;

c.height = 3;

c.volume = c.base.width * c.base.length * c.height;




return c;

}




void move(struct cuboid *c, int deltaX, int deltaY)

{

c-&gt;origin.x += deltaX;

c-&gt;origin.y += deltaY;

}




void scale(struct cuboid *c, int factor)

{

c-&gt;base.width *= factor;

c-&gt;base.length *= factor;

c-&gt;height *= factor;

c-&gt;volume = c-&gt;base.width * c-&gt;base.length * c-&gt;height;

}




void printCuboid(char *name, struct cuboid *c)

{

printf(“Cuboid %s origin = (%d, %d)
”, name, c-&gt;origin.x, c-&gt;origin.y);

printf(“tBase width = %d  Base length = %d
”, c-&gt;base.width,

c-&gt;base.length);

printf(“tHeight = %d
”, c-&gt;height);

printf(“tVolume = %d

”, c-&gt;volume);

}

int equalSize(struct cuboid *c1, struct cuboid *c2)

{

int result = FALSE;




if (c1-&gt;base.width == c2-&gt;base.width) {

if (c1-&gt;base.length == c2-&gt;base.length) {

if (c1-&gt;height == c2-&gt;height) {

result = TRUE;

}

}

}




return result;

}




int main()

{

struct cuboid first, second;




first = newCuboid();

second = newCuboid();




printf(“Initial cuboid values:
”);

printCuboid(“first”, &amp;first);

printCuboid(“second”, &amp;second);




if (equalSize(&amp;first, &amp;second)) {

move(&amp;first, +3, -6);

scale(&amp;second, 4);

}




printf(“
Changed cuboid values:
”);

printCuboid(“first”, &amp;first);

printCuboid(“second”, &amp;second);

}




Implement all the subroutines above as unoptimized closed subroutines, using stack variables to store all local variables. Note that the function newCuboid() must have a local variable (called <em>c</em>) which is returned by value to main(), where it is assigned to the local variables <em>first</em> and <em>second</em>. In other words, create code similar to what the C compiler produces, even if it seems inefficient.




Also run the program in <em>gdb</em>, displaying the values of <em>first</em> and <em>second</em> after they have been set by function calls. You should show that the functions are working as expected. Capture the <em>gdb</em> session using the <em>script </em>UNIX command, and name the output file <em>script.txt</em>.  Name your program <em>assign4.asm</em>.




<strong>Other Requirements</strong>




Make sure your code is readable and fully documented, including identifying information at the top of each file. You must comment each line of assembly code. Your code should also be well designed:  make sure it is well organized, clear, and concise.




<strong>New Skills Needed for this Assignment:</strong>




<ul>

 <li>Implementation of structs and nested structs</li>

 <li>Implementation of subroutines in assembly</li>

 <li>Returning structs by value from functions</li>

 <li>Use of pointers as arguments to subroutines</li>

</ul>






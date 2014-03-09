// VU MIF INORMATIKA 2 GRUPE
// Norbert Zardin 1311008
// Papildomo elemento iterpimas i surikiuota eile rezultate gaunant eile kurios pakartotinai nereikia rikiuoti
// Programoje bus vartojama anglu kalba
program ElementInsert;

type list = ^element;
     element = record
         next : list;
         info : integer;
{           Next - goes to the next element in the list
            info - information of the current element in the list   }
            end;
            
            
            
//Find the location and add
procedure insertA(var FirstIn : list; NewNumber : integer);
{           NewNumber - new element we are going to add into the list
            FirstIn - the very start of the list                   }
    var Current, NewElement, Previous : list;
{           Current - Current element in the list
            Previous - Previous element in the list
            NewElement - will be used to add NewNumber to the list     }
begin
    Previous := nil;       //Sets the previous location to NONE
    Current := FirstIn;    //Sets the current location to the first one in the list
    while (Current <> nil) and (NewNumber > Current^.info) do
    //While New number is bigger than the element in the list, search for the element that is bigger than the new number
    //When found - stop the search
        begin
            Previous := Current;            //sets the previous number to the current one
            Current := Current^.next;
        end;
        new(NewElement);
        NewElement^.info := NewNumber;
        NewElement^.next := Current;
        if (Previous = nil) then
            FirstIn := NewElement
        else
            Previous^.next:=NewElement;
end;



//Print the list if asked for
procedure print(location : list);
begin
    Write('Your list is: ');
    while location <> nil do
        begin
            Write(location^.info,' ');  //prints the number and inserts a space in between
            location:= location^.next; //next location
        end;
    writeln; // easier to read in the console
end;


// Main program

var start     : list;
    number    : integer;
    selection : char;
{               start - start point in the list
                number - new element we are goint to enter into the list
                selection - a variable for us to select whether we want to print the list or not    }

begin
    Writeln('Enter the number you want to insert into the array, type in 0 to cancel.');
    Readln(number);
    Writeln;
    While number <> 0 do  // cancels the cycle
        begin
            insertA(start,number);
            Writeln; // for a better look
            Writeln('Print? [Y/N]');
            readln(selection);
            writeln; // for a better look
            if (selection = 'Y') or (selection = 'y')
                then print(start);
            writeln; // for a better look
            Writeln('Enter the number you want to insert into the array, type in 0 to cancel.'); //The proccess will repeat unil it is canceled
            Readln(number);
        end;
  Writeln;
  Writeln('Press any key to continue...');
  Readln;
end.
procedure Slow;
var
  i,j,k: integer;
begin
  for i:=1 to N do
    for j:=1 to N do
      for k:=1 to N do
        //какое-то действие
end;

procedure Fast;
var
  i,j: integer;
begin
  for i:=1 to N do
    for j:=1 to N do
      Slow;
end;

procedure Both;
begin
  Fast;
end;
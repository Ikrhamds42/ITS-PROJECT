# ITS-PROJECT
SOURCE CODE TUGAS AKHIR INTELIGENCE TRANSPORT SYSTEM

DJIKSTRA
procedure TForm2.dijkstraClick(Sender: TObject); 
var 
a,b:integer; 
st,fh:double; 
begin 
startDij.Caption:=timetostr(now); 
st:=time; 
awal:=(mulai.ItemIndex)+1; tujuan:=(akhir.ItemIndex)+1; 
if (awal=0) or (tujuan=0) then 
showmessage('harus diisi!!!') 
else 
begin 
  dij.Cells[awal,1]:=inttostr(1); 
  dij.Cells[awal,3]:=inttostr(awal); 
  jarak:=99999999; 
  if (awal<>0) and (tujuan<>0) then 
    begin 
      for b:=1 to 77 do 
      begin 
        if node.Cells[b,awal]<>'' then 
           begin 
dij.Cells[b,2]:=node.Cells[b,awal]; 
dij.Cells[b,3]:=inttostr(awal); 
           end; 
       end; 
       for b:=1 to 77 do 
        begin 
if dij.Cells[b,2]<>'' then 
if dij.Cells[b,1]<>'' then 
else 
  if strtofloat(dij.Cells[b,2]) < jarak then 
    jarak:=strtofloat(dij.Cells[b,2]); 
       end; for b:=1 to 77 do
for b:1 to 77 do

begin 
  if floattostr(jarak)=dij.Cells[b,2] then 
      dij.Cells[b,1]:=inttostr(1); 
end; 
            for b:=1 to 77 do 
begin 
   if dij.Cells[b,2]=floattostr(jarak) then 
       c:=b; 
end; 
                           nex; 
           end; 
         nextDij; 
         linDij.ColWidths[0]:=35; 
         linDij.Cells[0,0]:=' Jalur '; 
         a:=0; 
         for b:=77 downto 1 do 
            if dij.Cells[b,4]<>'' then 
begin 
  linDij.Cells[(1+a),0]:=dij.Cells[b,4]; 
  a:=a+1; 
end; 
          finishDij.Caption:=timetostr(now); 
          fh:=time; 
    end; 
startdij.Caption:=timetostr(fh-st); 
DijkstraStep.Enabled:=false; Next.Enabled:=false; 
Dijkstra.Enabled:=false; 
          end; 


ALGORITMA SEMUT
procedure TForm2.semutClick; 
var 
  st,fh,alpha,beta,p,p1,p2,sigma,sigmax,jalant:double; 
  b,a,c,e,f,baris:integer; 
begin 
  startant.Caption:=timetostr(now);
  st:=time; 
  alpha:=1; beta:=1; rho:=0.99; q:=1; m:=300; t:=0.01; max:=5; 
  awal:=(mulai.ItemIndex)+1; tujuan:=(akhir.ItemIndex)+1; 
  jalant:=10000000; f:=0; feromon; 
repeat 
    f:=f+1; 
    siklus; 
        for e:=1 to m do 
begin 
  awal:=(mulai.ItemIndex)+1; 
  studikasus; for a:=1 to 76 do 
      begin 
         clearant; 
         sigma:=0; 
         jalur.Cells[a,e]:=inttostr(awal); 
         for b:=1 to 76 do 
            begin 
if node.Cells[b,awal]<>'' then 
                                    begin 
sigmax:=(power(strtofloat(fer.Cells[b,awal]),         alpha))*(power((1/(strtofloat(node.Cells[b,awal]))),beta)); 
sigma:=sigma+sigmax; 
         end; 
    end; 
  sigma:=roundto(sigma,-4); 
ant.Cells[2,1]:=floattostr(sigma); 
p1:=100; 
p:=0; 
rand; 
for b:=1 to 76 do 
  if node.Cells[b,awal]<>'' then 
     begin
p2:=roundto(((power(strtofloat(fer.Cells[b,awa l]),alpha))*(power((1/(strtofloat(node.Cells[b,a 
wal]))),beta)))/sigma,-4); 
ant.Cells[b,2]:=floattostr(p2); 
p:=p+p2; 
ant.Cells[b,3]:=floattostr(p); 
if r<p then 
  if p<p1 then 
   p1:=p;
end;
         ant.Cells[1,4]:=floattostr(p1); 
           for b:=1 to 76 do 
if ant.Cells[b,3]=ant.Cells[1,4] then 
   begin 
      for c:=1 to m+1 do 
         begin 
node.Cells[awal,c]:=''; 
         end; 
       c:=b; 
    end; 
  awal:=c; 
end; 
           studikasus; 
           end; 
         hapus; 
         for b:=1 to m do 
           if jalur.Cells[75,b]<>'' then 
          if strtofloat(jalur.Cells[75,b])<>'' then
begin 
  for c:=1 to 30 do 
     linsemut.Cells[c,0]:=''; 
  	       jalant:=strtofloat(jalur.Cells[75,b]); 
                     baris:=b; 
                     a:=0; 
                     for c:=1 to 30 do 
                        if jalur.Cells[c,baris]<>'' then
begin 
  linSemut.Cells[(1+a),0]:=jalur.Cells[c,baris]; 
  a:=a+1; 
end; 
     end; 
until f=max; 
linSemut.ColWidths[0]:=35; 
linSemut.Cells[0,0]:=' Jalur '; 
hasilsemut.Lines.Add(''); 
hasilsemut.Lines.Add(' jarak '+inttostr((mulai.ItemIndex)+1)+' ke 
'+inttostr((akhir.ItemIndex)+1)+' = '+floattostr(jalant)); 
finishant.Caption:=timetostr(now); 
fh:=time; 
finishant.Caption:=timetostr(fh-st); 
          end;

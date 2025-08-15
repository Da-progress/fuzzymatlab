for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 
PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0
RM=[5875792.3 5875255.8 5875196.8 5875196.9 5875232.6; 4471634.7 4471462.8 4471407.5 4471307.4 4471248]

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x11=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y11=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x11,y11)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x11=[RM(2,1) RM(2,2)]
    y11=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x11,y11)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x11=[RM(2,1) RM(2,2) RM(2,3)]
    y11=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x11,y11)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x11=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y11=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x11,y11)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x11=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y11=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x11,y11)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x11=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y11=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x11,y11)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x11=[RM(2,1) RM(2,3)]
    y11=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x11,y11)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x11=[RM(2,1) RM(2,3) RM(2,4)]
    y11=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x11,y11)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x11=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y11=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x11,y11)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x11=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y11=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x11,y11)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x11=[RM(2,1)  RM(2,2)]
    y11=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x11,y11)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x11=[RM(2,1) RM(2,2) RM(2,4)]
    y11=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x11,y11)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x11=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y11=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x11,y11)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x11=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y11=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x11,y11)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x11=[RM(2,1) RM(2,2)]
    y11=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x11,y11)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x11=[RM(2,1) RM(2,2) RM(2,3)]
    y11=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x11,y11)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x11=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y11=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x11,y11)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2) 
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2) 
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2) 
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)
LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end

% Subprogram 2. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ;	  % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)t

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
LONGhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y14=[LatM1 LatH1]
x14=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y14=[LatM1 LatH1]
x14=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y14=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x14=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end


%idb=figure;
%plot(x15,y15)
%hold on
%plot(x16,y16)
%hold on

%idc = figure;
%plot(x15n,y15n)
%hold on

%idd= figure;
%plot(x15n,y15n)
%hold on
%plot(x16n,y16n)
%title('Desired route in meters')
%xlabel('longitude [m]')
%ylabel('latitude [m]')
%hold on
%)^2); ide= figure;
%plot(x11,y11)
%hold on
%plot(x14,y14)
%title('Desired route in degrees')
%xlabel('longitude [°]')
%ylabel('latitude [°]')
%hold on
end
if Si==0 K1=1
else K1=Emp
end
for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 
% Subprogram 1. Global planning

PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0
RM=[5875232.6 5875268.3 5875356.7 5875386.2 5875405.35; 4471248 4471188.6 4471180.8 4471178.2 4471164.05]*K1

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x21=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y21=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x21,y21)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x21=[RM(2,1) RM(2,2)]
    y21=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x21,y21)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x21=[RM(2,1) RM(2,2) RM(2,3)]
    y21=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x21,y21)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x21=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y21=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x21,y21)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x21=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y21=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x21,y21)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x21=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y21=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x21,y21)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x21=[RM(2,1) RM(2,3)]
    y21=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x21,y21)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x21=[RM(2,1) RM(2,3) RM(2,4)]
    y21=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x21,y21)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x21=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y21=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x21,y21)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x21=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y21=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x21,y21)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x21=[RM(2,1)  RM(2,2)]
    y21=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x21,y21)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x21=[RM(2,1) RM(2,2) RM(2,4)]
    y21=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x21,y21)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x21=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y21=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x21,y21)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x21=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y21=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x21,y21)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x21=[RM(2,1) RM(2,2)]
    y21=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x21,y21)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x21=[RM(2,1) RM(2,2) RM(2,3)]
    y21=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x21,y21)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x21=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y21=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x21,y21)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2)
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2)
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2)
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)

LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end

% Subprogram 1. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ; % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
Longhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3-(7915.70447*log10(tan((45+LatH3/2)*pi/180)*((1-e*sin(LatH3*pi/180))/(1+e*sin(LatH3*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk1/2)*pi/180)*((1-e*sin(LAThk1*pi/180))/(1+e*sin(LAThk1*pi/180))^(e/2))))*tan(c1*pi/180) 
if p3<length(unique(Turning3)) c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1-(7915.70447*log10(tan((45+LAThk1/2)*pi/180)*((1-e*sin(LAThk1*pi/180))/(1+e*sin(LAThk1*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk2/2)*pi/180)*((1-e*sin(LAThk2*pi/180))/(1+e*sin(LAThk2*pi/180))^(e/2))))*tan(c2*pi/180)
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2-(7915.70447*log10(tan((45+LAThk2/2)*pi/180)*((1-e*sin(LAThk2*pi/180))/(1+e*sin(LAThk2*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk3/2)*pi/180)*((1-e*sin(LAThk3*pi/180))/(1+e*sin(LAThk3*pi/180))^(e/2))))*tan(c3*pi/180)
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3)
else c4=Emp
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180)
LONGhk4=LONGhk3-(7915.70447*log10(tan((45+LAThk3/2)*pi/180)*((1-e*sin(LAThk3*pi/180))/(1+e*sin(LAThk3*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk4/2)*pi/180)*((1-e*sin(LAThk4*pi/180))/(1+e*sin(LAThk4*pi/180))^(e/2))))*tan(c4*pi/180)
if p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4)
else c5=Emp
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4-(7915.70447*log10(tan((45+LAThk4/2)*pi/180)*((1-e*sin(LAThk4*pi/180))/(1+e*sin(LAThk4*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk5/2)*pi/180)*((1-e*sin(LAThk5*pi/180))/(1+e*sin(LAThk5*pi/180))^(e/2))))*tan(c5*pi/180)
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5)
else c6=Emp
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5-(7915.70447*log10(tan((45+LAThk5/2)*pi/180)*((1-e*sin(LAThk5*pi/180))/(1+e*sin(LAThk5*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk6/2)*pi/180)*((1-e*sin(LAThk6*pi/180))/(1+e*sin(LAThk6*pi/180))^(e/2))))*tan(c6*pi/180)
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6)
else c7=Emp
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6-(7915.70447*log10(tan((45+LAThk6/2)*pi/180)*((1-e*sin(LAThk6*pi/180))/(1+e*sin(LAThk6*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk7/2)*pi/180)*((1-e*sin(LAThk7*pi/180))/(1+e*sin(LAThk7*pi/180))^(e/2))))*tan(c7*pi/180)
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7)
else c8=Emp
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7-(7915.70447*log10(tan((45+LAThk7/2)*pi/180)*((1-e*sin(LAThk7*pi/180))/(1+e*sin(LAThk7*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk8/2)*pi/180)*((1-e*sin(LAThk8*pi/180))/(1+e*sin(LAThk8*pi/180))^(e/2))))*tan(c8*pi/180)
if p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8)
else c9=Emp
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8-(7915.70447*log10(tan((45+LAThk8/2)*pi/180)*((1-e*sin(LAThk8*pi/180))/(1+e*sin(LAThk8*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk9/2)*pi/180)*((1-e*sin(LAThk9*pi/180))/(1+e*sin(LAThk9*pi/180))^(e/2))))*tan(c9*pi/180)
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9)
else c10=Emp
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9-(7915.70447*log10(tan((45+LAThk9/2)*pi/180)*((1-e*sin(LAThk9*pi/180))/(1+e*sin(LAThk9*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk10/2)*pi/180)*((1-e*sin(LAThk10*pi/180))/(1+e*sin(LAThk10*pi/180))^(e/2))))*tan(c10*pi/180)
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10)
else c11=Emp
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10-(7915.70447*log10(tan((45+LAThk10/2)*pi/180)*((1-e*sin(LAThk10*pi/180))/(1+e*sin(LAThk10*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk11/2)*pi/180)*((1-e*sin(LAThk11*pi/180))/(1+e*sin(LAThk11*pi/180))^(e/2))))*tan(c11*pi/180)
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11)
else c12=Emp
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11-(7915.70447*log10(tan((45+LAThk11/2)*pi/180)*((1-e*sin(LAThk11*pi/180))/(1+e*sin(LAThk11*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk12/2)*pi/180)*((1-e*sin(LAThk12*pi/180))/(1+e*sin(LAThk12*pi/180))^(e/2))))*tan(c12*pi/180)
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12)
else c13=Emp
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12-(7915.70447*log10(tan((45+LAThk12/2)*pi/180)*((1-e*sin(LAThk12*pi/180))/(1+e*sin(LAThk12*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk13/2)*pi/180)*((1-e*sin(LAThk13*pi/180))/(1+e*sin(LAThk13*pi/180))^(e/2))))*tan(c13*pi/180)
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13)
else c14=Emp
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13-(7915.70447*log10(tan((45+LAThk13/2)*pi/180)*((1-e*sin(LAThk13*pi/180))/(1+e*sin(LAThk13*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk14/2)*pi/180)*((1-e*sin(LAThk14*pi/180))/(1+e*sin(LAThk14*pi/180))^(e/2))))*tan(c14*pi/180)
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14)
else c15=Emp
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14-(7915.70447*log10(tan((45+LAThk14/2)*pi/180)*((1-e*sin(LAThk14*pi/180))/(1+e*sin(LAThk14*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk15/2)*pi/180)*((1-e*sin(LAThk15*pi/180))/(1+e*sin(LAThk15*pi/180))^(e/2))))*tan(c15*pi/180)
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15)
else c16=Emp
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15-(7915.70447*log10(tan((45+LAThk15/2)*pi/180)*((1-e*sin(LAThk15*pi/180))/(1+e*sin(LAThk15*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk16/2)*pi/180)*((1-e*sin(LAThk16*pi/180))/(1+e*sin(LAThk16*pi/180))^(e/2))))*tan(c16*pi/180)
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16)
else c17=Emp
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16-(7915.70447*log10(tan((45+LAThk16/2)*pi/180)*((1-e*sin(LAThk16*pi/180))/(1+e*sin(LAThk16*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk17/2)*pi/180)*((1-e*sin(LAThk17*pi/180))/(1+e*sin(LAThk17*pi/180))^(e/2))))*tan(c17*pi/180)
if p3+17<=length(unique(Turning3)) c18=Turning3(1,p3+17)
else c18=Emp
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17-(7915.70447*log10(tan((45+LAThk17/2)*pi/180)*((1-e*sin(LAThk17*pi/180))/(1+e*sin(LAThk17*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk18/2)*pi/180)*((1-e*sin(LAThk18*pi/180))/(1+e*sin(LAThk18*pi/180))^(e/2))))*tan(c18*pi/180)
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18)
else c19=Emp
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18-(7915.70447*log10(tan((45+LAThk18/2)*pi/180)*((1-e*sin(LAThk18*pi/180))/(1+e*sin(LAThk18*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk19/2)*pi/180)*((1-e*sin(LAThk19*pi/180))/(1+e*sin(LAThk19*pi/180))^(e/2))))*tan(c19*pi/180)
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19)
else c20=Emp
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19-(7915.70447*log10(tan((45+LAThk19/2)*pi/180)*((1-e*sin(LAThk19*pi/180))/(1+e*sin(LAThk19*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk20/2)*pi/180)*((1-e*sin(LAThk20*pi/180))/(1+e*sin(LAThk20*pi/180))^(e/2))))*tan(c20*pi/180)
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20)
else c21=Emp
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20-(7915.70447*log10(tan((45+LAThk20/2)*pi/180)*((1-e*sin(LAThk20*pi/180))/(1+e*sin(LAThk20*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk21/2)*pi/180)*((1-e*sin(LAThk21*pi/180))/(1+e*sin(LAThk21*pi/180))^(e/2))))*tan(c21*pi/180)
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21)
else c22=Emp
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21-(7915.70447*log10(tan((45+LAThk21/2)*pi/180)*((1-e*sin(LAThk21*pi/180))/(1+e*sin(LAThk21*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk22/2)*pi/180)*((1-e*sin(LAThk22*pi/180))/(1+e*sin(LAThk22*pi/180))^(e/2))))*tan(c22*pi/180)
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22)
else c23=Emp
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22-(7915.70447*log10(tan((45+LAThk22/2)*pi/180)*((1-e*sin(LAThk22*pi/180))/(1+e*sin(LAThk22*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk23/2)*pi/180)*((1-e*sin(LAThk23*pi/180))/(1+e*sin(LAThk23*pi/180))^(e/2))))*tan(c23*pi/180)
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23)
else c24=Emp
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23-(7915.70447*log10(tan((45+LAThk23/2)*pi/180)*((1-e*sin(LAThk23*pi/180))/(1+e*sin(LAThk23*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk24/2)*pi/180)*((1-e*sin(LAThk24*pi/180))/(1+e*sin(LAThk24*pi/180))^(e/2))))*tan(c24*pi/180)
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24)
else c25=Emp
end
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180);
LONGhk25=LONGhk24-(7915.70447*log10(tan((45+LAThk24/2)*pi/180)*((1-e*sin(LAThk24*pi/180))/(1+e*sin(LAThk24*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk25/2)*pi/180)*((1-e*sin(LAThk25*pi/180))/(1+e*sin(LAThk25*pi/180))^(e/2))))*tan(c25*pi/180)
if p3+25<=length(unique(Turning3)) c26=Turning3(1, p3+25)
else c26=Emp
end
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25-(7915.70447*log10(tan((45+LAThk25/2)*pi/180)*((1-e*sin(LAThk25*pi/180))/(1+e*sin(LAThk25*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk26/2)*pi/180)*((1-e*sin(LAThk26*pi/180))/(1+e*sin(LAThk26*pi/180))^(e/2))))*tan(c26*pi/180)
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26)
else c27=Emp
end
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26-(7915.70447*log10(tan((45+LAThk26/2)*pi/180)*((1-e*sin(LAThk26*pi/180))/(1+e*sin(LAThk26*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk27/2)*pi/180)*((1-e*sin(LAThk27*pi/180))/(1+e*sin(LAThk27*pi/180))^(e/2))))*tan(c27*pi/180)
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27)
else c28=Emp
end
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27-(7915.70447*log10(tan((45+LAThk27/2)*pi/180)*((1-e*sin(LAThk27*pi/180))/(1+e*sin(LAThk27*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk28/2)*pi/180)*((1-e*sin(LAThk28*pi/180))/(1+e*sin(LAThk28*pi/180))^(e/2))))*tan(c28*pi/180)
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28)
else c29=Emp
end
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28-(7915.70447*log10(tan((45+LAThk28/2)*pi/180)*((1-e*sin(LAThk28*pi/180))/(1+e*sin(LAThk28*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk29/2)*pi/180)*((1-e*sin(LAThk29*pi/180))/(1+e*sin(LAThk29*pi/180))^(e/2))))*tan(c29*pi/180)
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29)
else c30=Emp
end
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29-(7915.70447*log10(tan((45+LAThk29/2)*pi/180)*((1-e*sin(LAThk29*pi/180))/(1+e*sin(LAThk29*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk30/2)*pi/180)*((1-e*sin(LAThk30*pi/180))/(1+e*sin(LAThk30*pi/180))^(e/2))))*tan(c30*pi/180)
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30)
else c31=Emp
end
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30-(7915.70447*log10(tan((45+LAThk30/2)*pi/180)*((1-e*sin(LAThk30*pi/180))/(1+e*sin(LAThk30*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk31/2)*pi/180)*((1-e*sin(LAThk31*pi/180))/(1+e*sin(LAThk31*pi/180))^(e/2))))*tan(c31*pi/180)
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31)
else c32=Emp
end
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31-(7915.70447*log10(tan((45+LAThk31/2)*pi/180)*((1-e*sin(LAThk31*pi/180))/(1+e*sin(LAThk31*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk32/2)*pi/180)*((1-e*sin(LAThk32*pi/180))/(1+e*sin(LAThk32*pi/180))^(e/2))))*tan(c32*pi/180)
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32-(7915.70447*log10(tan((45+LAThk32/2)*pi/180)*((1-e*sin(LAThk32*pi/180))/(1+e*sin(LAThk32*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk33/2)*pi/180)*((1-e*sin(LAThk33*pi/180))/(1+e*sin(LAThk33*pi/180))^(e/2))))*tan(c33*pi/180)
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33)
else c34=Emp
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33-(7915.70447*log10(tan((45+LAThk33/2)*pi/180)*((1-e*sin(LAThk33*pi/180))/(1+e*sin(LAThk33*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk34/2)*pi/180)*((1-e*sin(LAThk34*pi/180))/(1+e*sin(LAThk34*pi/180))^(e/2))))*tan(c34*pi/180)
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34)
else c35=Emp
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34-(7915.70447*log10(tan((45+LAThk34/2)*pi/180)*((1-e*sin(LAThk34*pi/180))/(1+e*sin(LAThk34*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk35/2)*pi/180)*((1-e*sin(LAThk35*pi/180))/(1+e*sin(LAThk35*pi/180))^(e/2))))*tan(c35*pi/180)
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35)
else c36=Emp
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35-(7915.70447*log10(tan((45+LAThk35/2)*pi/180)*((1-e*sin(LAThk35*pi/180))/(1+e*sin(LAThk35*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk36/2)*pi/180)*((1-e*sin(LAThk36*pi/180))/(1+e*sin(LAThk36*pi/180))^(e/2))))*tan(c36*pi/180)
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36)
else c37=Emp
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36-(7915.70447*log10(tan((45+LAThk36/2)*pi/180)*((1-e*sin(LAThk36*pi/180))/(1+e*sin(LAThk36*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk37/2)*pi/180)*((1-e*sin(LAThk37*pi/180))/(1+e*sin(LAThk37*pi/180))^(e/2))))*tan(c37*pi/180)
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37)
else c38=Emp
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37-(7915.70447*log10(tan((45+LAThk37/2)*pi/180)*((1-e*sin(LAThk37*pi/180))/(1+e*sin(LAThk37*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk38/2)*pi/180)*((1-e*sin(LAThk38*pi/180))/(1+e*sin(LAThk38*pi/180))^(e/2))))*tan(c38*pi/180)
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38)
else c39=Emp
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38-(7915.70447*log10(tan((45+LAThk38/2)*pi/180)*((1-e*sin(LAThk38*pi/180))/(1+e*sin(LAThk38*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk39/2)*pi/180)*((1-e*sin(LAThk39*pi/180))/(1+e*sin(LAThk39*pi/180))^(e/2))))*tan(c39*pi/180)
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39)
else c40=Emp
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39-(7915.70447*log10(tan((45+LAThk39/2)*pi/180)*((1-e*sin(LAThk39*pi/180))/(1+e*sin(LAThk39*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk40/2)*pi/180)*((1-e*sin(LAThk40*pi/180))/(1+e*sin(LAThk40*pi/180))^(e/2))))*tan(c40*pi/180)
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40)
else c41=Emp
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40-(7915.70447*log10(tan((45+LAThk40/2)*pi/180)*((1-e*sin(LAThk40*pi/180))/(1+e*sin(LAThk40*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk41/2)*pi/180)*((1-e*sin(LAThk41*pi/180))/(1+e*sin(LAThk41*pi/180))^(e/2))))*tan(c41*pi/180)
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41)
else c42=Emp
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41-(7915.70447*log10(tan((45+LAThk41/2)*pi/180)*((1-e*sin(LAThk41*pi/180))/(1+e*sin(LAThk41*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk42/2)*pi/180)*((1-e*sin(LAThk42*pi/180))/(1+e*sin(LAThk42*pi/180))^(e/2))))*tan(c42*pi/180)
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42)
else c43=Emp
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42-(7915.70447*log10(tan((45+LAThk42/2)*pi/180)*((1-e*sin(LAThk42*pi/180))/(1+e*sin(LAThk42*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk43/2)*pi/180)*((1-e*sin(LAThk43*pi/180))/(1+e*sin(LAThk43*pi/180))^(e/2))))*tan(c43*pi/180)
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43)
else c44=Emp
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43-(7915.70447*log10(tan((45+LAThk43/2)*pi/180)*((1-e*sin(LAThk43*pi/180))/(1+e*sin(LAThk43*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk44/2)*pi/180)*((1-e*sin(LAThk44*pi/180))/(1+e*sin(LAThk44*pi/180))^(e/2))))*tan(c44*pi/180)
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44)
else c45=Emp
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44-(7915.70447*log10(tan((45+LAThk44/2)*pi/180)*((1-e*sin(LAThk44*pi/180))/(1+e*sin(LAThk44*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk45/2)*pi/180)*((1-e*sin(LAThk45*pi/180))/(1+e*sin(LAThk45*pi/180))^(e/2))))*tan(c45*pi/180)
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45)
else c46=Emp
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45-(7915.70447*log10(tan((45+LAThk45/2)*pi/180)*((1-e*sin(LAThk45*pi/180))/(1+e*sin(LAThk45*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk46/2)*pi/180)*((1-e*sin(LAThk46*pi/180))/(1+e*sin(LAThk46*pi/180))^(e/2))))*tan(c46*pi/180)
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46)
else c47=Emp
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46-(7915.70447*log10(tan((45+LAThk46/2)*pi/180)*((1-e*sin(LAThk46*pi/180))/(1+e*sin(LAThk46*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk47/2)*pi/180)*((1-e*sin(LAThk47*pi/180))/(1+e*sin(LAThk47*pi/180))^(e/2))))*tan(c47*pi/180)
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47)
else c48=Emp
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47-(7915.70447*log10(tan((45+LAThk47/2)*pi/180)*((1-e*sin(LAThk47*pi/180))/(1+e*sin(LAThk47*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk48/2)*pi/180)*((1-e*sin(LAThk48*pi/180))/(1+e*sin(LAThk48*pi/180))^(e/2))))*tan(c48*pi/180)
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48)
else c49=Emp
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48-(7915.70447*log10(tan((45+LAThk48/2)*pi/180)*((1-e*sin(LAThk48*pi/180))/(1+e*sin(LAThk48*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk49/2)*pi/180)*((1-e*sin(LAThk49*pi/180))/(1+e*sin(LAThk49*pi/180))^(e/2))))*tan(c49*pi/180)
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49)
else c50=Emp
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49-(7915.70447*log10(tan((45+LAThk49/2)*pi/180)*((1-e*sin(LAThk49*pi/180))/(1+e*sin(LAThk49*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk50/2)*pi/180)*((1-e*sin(LAThk50*pi/180))/(1+e*sin(LAThk50*pi/180))^(e/2))))*tan(c50*pi/180)
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50)
else c51=Emp
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50-(7915.70447*log10(tan((45+LAThk50/2)*pi/180)*((1-e*sin(LAThk50*pi/180))/(1+e*sin(LAThk50*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk51/2)*pi/180)*((1-e*sin(LAThk51*pi/180))/(1+e*sin(LAThk51*pi/180))^(e/2))))*tan(c51*pi/180)
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51)
else c52=Emp
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51-(7915.70447*log10(tan((45+LAThk51/2)*pi/180)*((1-e*sin(LAThk51*pi/180))/(1+e*sin(LAThk51*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk52/2)*pi/180)*((1-e*sin(LAThk52*pi/180))/(1+e*sin(LAThk52*pi/180))^(e/2))))*tan(c52*pi/180)
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52)
else c53=Emp
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52-(7915.70447*log10(tan((45+LAThk52/2)*pi/180)*((1-e*sin(LAThk52*pi/180))/(1+e*sin(LAThk52*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk53/2)*pi/180)*((1-e*sin(LAThk53*pi/180))/(1+e*sin(LAThk53*pi/180))^(e/2))))*tan(c53*pi/180)
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53)
else c54=Emp
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53-(7915.70447*log10(tan((45+LAThk53/2)*pi/180)*((1-e*sin(LAThk53*pi/180))/(1+e*sin(LAThk53*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk54/2)*pi/180)*((1-e*sin(LAThk54*pi/180))/(1+e*sin(LAThk54*pi/180))^(e/2))))*tan(c54*pi/180)
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54)
else c55=Emp
end
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54-(7915.70447*log10(tan((45+LAThk54/2)*pi/180)*((1-e*sin(LAThk54*pi/180))/(1+e*sin(LAThk54*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk55/2)*pi/180)*((1-e*sin(LAThk55*pi/180))/(1+e*sin(LAThk55*pi/180))^(e/2))))*tan(c55*pi/180)
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55)
else c56=Emp
end
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55-(7915.70447*log10(tan((45+LAThk55/2)*pi/180)*((1-e*sin(LAThk55*pi/180))/(1+e*sin(LAThk55*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk56/2)*pi/180)*((1-e*sin(LAThk56*pi/180))/(1+e*sin(LAThk56*pi/180))^(e/2))))*tan(c56*pi/180)
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56)
else c57=Emp
end
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56-(7915.70447*log10(tan((45+LAThk56/2)*pi/180)*((1-e*sin(LAThk56*pi/180))/(1+e*sin(LAThk56*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk57/2)*pi/180)*((1-e*sin(LAThk57*pi/180))/(1+e*sin(LAThk57*pi/180))^(e/2))))*tan(c57*pi/180)
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57)
else c58=Emp
end
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57-(7915.70447*log10(tan((45+LAThk57/2)*pi/180)*((1-e*sin(LAThk57*pi/180))/(1+e*sin(LAThk57*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk58/2)*pi/180)*((1-e*sin(LAThk58*pi/180))/(1+e*sin(LAThk58*pi/180))^(e/2))))*tan(c58*pi/180)
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58)
else c59=Emp
end
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58-(7915.70447*log10(tan((45+LAThk58/2)*pi/180)*((1-e*sin(LAThk58*pi/180))/(1+e*sin(LAThk58*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk59/2)*pi/180)*((1-e*sin(LAThk59*pi/180))/(1+e*sin(LAThk59*pi/180))^(e/2))))*tan(c59*pi/180)
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59)
else c60=Emp
end
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59-(7915.70447*log10(tan((45+LAThk59/2)*pi/180)*((1-e*sin(LAThk59*pi/180))/(1+e*sin(LAThk59*pi/180))^(e/2)))-7915.70447*log10(tan((45+LAThk60/2)*pi/180)*((1-e*sin(LAThk60*pi/180))/(1+e*sin(LAThk60*pi/180))^(e/2))))*tan(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y24=[LatM1 LatH1]
x24=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y24=[LatM1 LatH1]
x24=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y24=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x24=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end


%idb=figure;
%plot(x25,y25)
%hold on
%plot(x26,y26)
%hold on

%idc = figure;
%plot(x25n,y25n)
%hold on

%idd= figure;
%plot(x25n,y25n)
%hold on
%plot(x26n,y26n)
%title('Desired route in meters')
%xlabel('longitude [m]')
%ylabel('latitude [m]')
%hold on
%ide= figure;
%plot(x21,y21)
%hold on
%plot(x24,y24)
%title('Desired route in degrees')
%xlabel('longitude [°]')
%ylabel('latitude [°]')
%hold on
end

% Subprogram 1. Global planning
digitsOLd=digits(9)
if K1==Emp K2=Emp
elseif Si==0 K2=1
else K2=Emp
end 

for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 
PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0
RM=[5875405.35 5875424.5 5875389.4 5875309.9 5875259.65; 4471164.05 4471149.9 4471126.2 4471138.4 4471179.85]*K2

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x31=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y31=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x31,y31)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x31=[RM(2,1) RM(2,2)]
    y31=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x31,y31)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x31=[RM(2,1) RM(2,2) RM(2,3)]
    y31=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x31,y31)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x31=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y31=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x31,y31)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x31=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y31=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x31,y31)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x31=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y31=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x31,y31)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x31=[RM(2,1) RM(2,3)]
    y31=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x31,y31)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x31=[RM(2,1) RM(2,3) RM(2,4)]
    y31=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x31,y31)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x31=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y31=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x31,y31)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x31=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y31=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x31,y31)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x31=[RM(2,1)  RM(2,2)]
    y31=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x31,y31)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x31=[RM(2,1) RM(2,2) RM(2,4)]
    y31=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x31,y31)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x31=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y31=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x31,y31)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x31=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y31=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x31,y31)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x31=[RM(2,1) RM(2,2)]
    y31=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x31,y31)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x31=[RM(2,1) RM(2,2) RM(2,3)]
    y31=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x31,y31)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x31=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y31=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x31,y31)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2)
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2)
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2)
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)

LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end


% Subprogram 2. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ;	  % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
Longhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y34=[LatM1 LatH1]
x34=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y34=[LatM1 LatH1]
x34=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y34=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x34=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end


%idb=figure;
%plot(x35,y35)
%hold on
%plot(x36,y36)
%hold on

%idc = figure;
%plot(x35n,y35n)
%hold on

%idd= figure;
%plot(x35n,y35n)
%hold on
%plot(x3
% 6n,y36n)
%title('Desired route in meters')
%xlabel('longitude [m]')
%ylabel('latitude [m]')
%hold on
%ide= figure;
%plot(x31,y31)
%hold on
%plot(x34,y34)
%title('Desired route in degrees')
%xlabel('longitude [°]')
%ylabel('latitude [°]')
%hold on
end

% Subprogram 1. Global planning
if K2==Emp K3=Emp
elseif Si==0 K3=1 
else K3=Emp
end 

for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 

PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0

RM=[5875259.65 5875209.4 5875129.0 5875150.0 5875207.4; 4471179.85 4471221.3 4471433.9 4471502.8 4471526.4]*K3

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x41=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y41=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x41,y41)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x41=[RM(2,1) RM(2,2)]
    y41=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x41,y41)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x41=[RM(2,1) RM(2,2) RM(2,3)]
    y41=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x41,y41)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x41=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y41=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x41,y41)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x41=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y41=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x41,y41)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x41=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y41=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x41,y41)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x41=[RM(2,1) RM(2,3)]
    y41=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x41,y41)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x41=[RM(2,1) RM(2,3) RM(2,4)]
    y41=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x41,y41)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x41=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y41=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x41,y41)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x41=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y41=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x41,y41)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x41=[RM(2,1)  RM(2,2)]
    y41=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x41,y41)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x41=[RM(2,1) RM(2,2) RM(2,4)]
    y41=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x41,y41)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x41=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y41=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x41,y41)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x41=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y41=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x41,y41)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x41=[RM(2,1) RM(2,2)]
    y41=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x41,y41)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x41=[RM(2,1) RM(2,2) RM(2,3)]
    y41=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x41,y41)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x41=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y41=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x41,y41)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2)
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2)
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2)
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)

LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end

% Subprogram 1. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ;	  % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
Longhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y44=[LatM1 LatH1]
x44=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y44=[LatM1 LatH1]
x44=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y44=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x44=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end


%idb=figure;
%plot(x45,y45)
%hold on
%plot(x46,y46)
%hold on

%idc = figure;
%plot(x45n,y45n)
%hold on

%idd= figure;
%plot(x45n,y45n)
%hold on
%plot(x46n,y46n)
%title('Desired route in meters')
%xlabel('longitude [m]')
%ylabel('latitude [m]')
%hold on
%ide= figure;
%plot(x41,y41)
%hold on
end

% Subprogram 1. Global planning
if K3==Emp K4=Emp
elseif Si==0 K4=1 
else K4=Emp 
end

for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 

PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0
RM=[5875207.4 5875264.8 5875598.2 5875690.6 5875763.1; 4471526.4 4471550 4471519.7 4471522.8 4471586.6]*K4

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x51=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y51=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x51,y51)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x51=[RM(2,1) RM(2,2)]
    y51=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x51,y51)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x51=[RM(2,1) RM(2,2) RM(2,3)]
    y51=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x51,y51)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x51=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y51=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x51,y51)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x51=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y51=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x51,y51)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x51=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y51=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x51,y51)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x51=[RM(2,1) RM(2,3)]
    y51=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x51,y51)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x51=[RM(2,1) RM(2,3) RM(2,4)]
    y51=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x51,y51)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x51=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y51=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x51,y51)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x51=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y51=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x51,y51)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x51=[RM(2,1)  RM(2,2)]
    y51=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x51,y51)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x51=[RM(2,1) RM(2,2) RM(2,4)]
    y51=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x51,y51)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x51=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y51=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x51,y51)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x51=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y51=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x51,y51)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x51=[RM(2,1) RM(2,2)]
    y51=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x51,y51)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x51=[RM(2,1) RM(2,2) RM(2,3)]
    y51=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x51,y51)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x51=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y51=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x51,y51)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2)
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2)
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2)
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)

LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end
% Subprogram 1. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ;	  % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
Longhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y54=[LatM1 LatH1]
x54=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y54=[LatM1 LatH1]
x54=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y54=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x54=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end
end

% Subprogram 1. Global planning
if K4==Emp K5=Emp
elseif Si==0 K5=1 
else K5=Emp 
end 
for e=sqrt(2/298.257223563-(1/298.257223563)^2); Rwgs84=3443.918467; 

PM0=[0 1 0 0 0;-1 0 1 0 0;0 -1 0 1 0;0 0 -1 0 1;0 0 0 -1 0]
S1p2=[0 0 0 0 0;0 1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S1p3=[0 0 0 0 0;0 0 0 0 0;0 0 1 0 0;0 0 0 0 0;0 0 0 0 0]
S1p4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 1 0;0 0 0 0 0]
S1p5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 1]
S2a2=[0 0 0 0 0;0 -1 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0]
S2a3=[0 0 0 0 0;0 0 0 0 0;0 0 -1 0 0;0 0 0 0 0;0 0 0 0 0]
S2a4=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 -1 0;0 0 0 0 0]
S2a5=[0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 0;0 0 0 0 -1]
S2=[0 -1 1 0 0; 1 0 -1 1 0; -1 1 0 -1 1; 0 0 1 0 -1; 0 0 -1 1 0] % skipping p.2
S3=[0 0 0 0 0; 0 0 -1 1 0;0	1 0	-1 1; 0	-1 1 0 -1; 0 0 0 1 0] % skipping p.3
S4=[0 0 0 0 0; 0 0 0 0 0; 0 0 0 -1 1; 0	0 1	0 -1; 0	0 -1 1 0] % skipping p.4
Si=0
S0=S2
S=Si+S0
PM=PM0+S
RM=[5875763.1 5875768.25 5875773.4 5875796.8 5875791.5; 4471586.6 4471591.15 4471595.7 4471586.9 4471572.9]*K5

%ida = figure;

if PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x61=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y61=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x61,y61)
 elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(2,2))==1
    
    x61=[RM(2,1) RM(2,2)]
    y61=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x61,y61)   
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(3,3))==1
    
    x61=[RM(2,1) RM(2,2) RM(2,3)]
    y61=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    %plot(x61,y61)
elseif PM(1,2)~=0 && PM(2,3)~=0 && PM(3,4)~=0 && abs(PM(4,4))==1
         
    x61=[RM(2,1) RM(2,2) RM(2,3) RM(2,4)]
    y61=[RM(1,1) RM(1,2) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x61,y61)
elseif PM(1,2)~=0 && PM(2,3)~=0 &&  PM(3,4)~=0 && abs(PM(5,5))==1
    
    x61=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y61=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,4) RM(1,5)]
    %plot (x61,y61)
elseif PM(1,2)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1
     
   x61=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y61=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
   x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
   y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x61,y61)
    
elseif PM(1,2)==0 && abs(PM(3,3))==1
    
    x61=[RM(2,1) RM(2,3)]
    y61=[RM(1,1) RM(1,3)]
    x1=[RM(2,1) RM(2,3) RM(2,4)]
    y1=[RM(1,1) RM(1,3) RM(1,4)]
    %plot(x61,y61)
elseif PM(1,2)==0 && abs(PM(4,4))==1
         
    x61=[RM(2,1) RM(2,3) RM(2,4)]
    y61=[RM(1,1) RM(1,3) RM(1,4)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x61,y61)
elseif PM(1,2)==0 && abs(PM(5,5))==1
    
    x61=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y61=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,3) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,3) RM(1,4) RM(1,5)]
    %plot(x61,y61)
elseif PM(2,3)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
    x61=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y61=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x61,y61)    
elseif PM(2,3)==0 && abs(PM(2,2))==1
         
    x61=[RM(2,1)  RM(2,2)]
    y61=[RM(1,1)  RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,4)]
    y1=[RM(1,1) RM(1,2) RM(1,4)]
    %plot(x61,y61)
elseif PM(2,3)==0 && abs(PM(4,4))==1
         
    x61=[RM(2,1) RM(2,2) RM(2,4)]
    y61=[RM(1,1) RM(1,2) RM(1,4)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot(x61,y61)
elseif PM(2,3)==0 && abs(PM(5,5))==1
    
    x61=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y61=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,4) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,4) RM(1,5)]
    %plot (x61,y61)
elseif PM(3,4)==0 && abs(PM(2,2))~=1 && abs(PM(3,3))~=1 && abs(PM(4,4))~=1 && abs(PM(5,5))~=1 
     
   x61=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y61=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
   x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
   y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x61,y61)
elseif PM(3,4)==0 && abs(PM(2,2))==1
         
    x61=[RM(2,1) RM(2,2)]
    y61=[RM(1,1) RM(1,2)]
    x1=[RM(2,1) RM(2,2) RM(2,3)]
    y1=[RM(1,1) RM(1,2) RM(1,3)]
    %plot(x61,y61)
elseif PM(3,4)==0 && abs(PM(3,3))==1
         
    x61=[RM(2,1) RM(2,2) RM(2,3)]
    y61=[RM(1,1) RM(1,2) RM(1,3)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot(x61,y61)
elseif PM(3,4)==0 && PM(5,5)==1
    
    x61=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y61=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    x1=[RM(2,1) RM(2,2) RM(2,3) RM(2,5)]
    y1=[RM(1,1) RM(1,2) RM(1,3) RM(1,5)]
    %plot (x61,y61)     
end
Longit=x1
Latit=y1
%title('Trajektoria zadana w stopniach')
%xlabel('longitude [deg]')
%ylabel('latitude [deg]')

LatM1=Latit(1,1)
LongM1=Longit(1,1)
if max(length(unique(Latit)))>=2
LatM2=Latit(1,2)
LongM2=Longit(1,2)
else
LatM2=LatM1
LongM2=LongM1  
end
if max(length(unique(Latit)))>=3
LatM3=Latit(1,3)
LongM3=Longit(1,3)
else
LatM3=LatM2
LongM3=LongM2
end
if max(length(unique(Latit)))>=4
LatM4=Latit(1,4)
LongM4=Longit(1,4)
else
LatM4=LatM3
LongM4=LongM3
end
if max(length(unique(Latit)))>=5
LatM5=Latit(1,5)
LongM5=Longit(1,5) 
else 
LatM5=LatM4
LongM5=LongM4
end

D1=sqrt((LatM2-LatM1)^2+(LongM2-LongM1)^2)
D2=sqrt((LatM3-LatM2)^2+(LongM3-LongM2)^2)
D3=sqrt((LatM4-LatM3)^2+(LongM4-LongM3)^2)
D4=sqrt((LatM5-LatM4)^2+(LongM5-LongM4)^2)

LAT1r=LatM1*pi/180; %convert latitude to radians
LAT2r=LatM2*pi/180; %convert latitude to radians
LONG1r=-LongM1*pi/180; %convert longitude to radians with opposite sign
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG1rd=LongM1*pi/180; %convert longitude to radians without opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
if LatM2-LatM1<0
   TC1=mod(acos((LongM2-LongM1)/D1)*180/pi+90,360)
elseif LatM2-LatM1>=0
   TC1=mod(asin((LongM2-LongM1)/D1)*180/pi,360)
end
LAT2r=LatM2*pi/180; %convert latitude to radians
LAT3r=LatM3*pi/180; %convert latitude to radians
LONG2r=-LongM2*pi/180; %convert longitude to radians with opposite sign
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG2rd=LongM2*pi/180; %convert longitude to radians without opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
if LatM3-LatM2<0
   TC2=mod(acos((LongM3-LongM2)/D2)*180/pi+90,360)
elseif LatM3-LatM2>=0
   TC2=mod(asin((LongM3-LongM2)/D2)*180/pi,360)
end
LAT3r=LatM3*pi/180; %convert latitude to radians
LAT4r=LatM4*pi/180; %convert latitude to radians
LONG3r=-LongM3*pi/180; %convert longitude to radians with opposite sign
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG3rd=LongM3*pi/180; %convert longitude to radians without opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
if LatM4-LatM3<0
   TC3=mod(acos((LongM4-LongM3)/D3)*180/pi+90,360)
elseif LatM4-LatM3>=0
   TC3=mod(asin((LongM4-LongM3)/D3)*180/pi,360)
end
LAT4r=LatM4*pi/180; %convert latitude to radians
LAT5r=LatM5*pi/180; %convert latitude to radians
LONG4r=-LongM4*pi/180; %convert longitude to radians with opposite sign
LONG5r=-LongM5*pi/180; %convert longitude to radians with opposite sign
LONG4rd=LongM4*pi/180; %convert longitude to radians without opposite sign
LONG5rd=LongM5*pi/180; %convert longitude to radians without opposite sign
if LatM5-LatM4<0
   TC4=mod(acos((LongM5-LongM4)/D4)*180/pi+90,360)
elseif LatM5-LatM4>=0
   TC4=mod(asin((LongM5-LongM4)/D4)*180/pi,360)
end
% Subprogram 1. Local planning

%Ship "BLUE LADY"
% Zadane dani dla wyznaczenia charakterystyk manewrowych statka "UMM QARN" IMO: 9732333	
								
%Parametry  jdn pomiarowe						
LPP=13.5;	
LOA=13.78;
B=2.38;	
Ns=1; Nst=1;				
%Typ zarządzenia energetycznego	SP	
	 					
Z=4;		  % Ilość skrzydeł śruby 						
Ds=0.384 ;       % Średnica, м.					
H=0.4 ;       % Skok
HDs = 0.861;  %  Współczynnik skoku H / Ds		
Q=0.65;	      %  Współczynnik powierzchni skrzydeł						
%Charakterystyka steru: 							
A=0.202;	  % Powierzchnia płetwy sterowej, м².						
h=0.6;	  % Wysokość stera,м.					
fr=0.34;       % Obszar podcięcia rufy,м2.					
delta1=35;	  % Kąt wychylenia steru, stopnie

%Eksperyment cyrkulacji w stanie balastowym:							
Vp1=13.50;	  % Prędkość początkowa, w				
Vk1=7.2;	                  
lb1=45/13.5   ;	  % Wysunąć, kadłuby						
lb1=15/13.5   ;	  % Przesunięcie boczne
dt1=30/13.5  ;	  % Średnica taktyczna, kadłuby						
du1=20/13.5   ;	  % Średnica ustalona, kadłuby	

%Eksperyment cyrkulacji w stanie załadowania:							
Vp2=12.50;	  % Prędkość początkowa, w				
Vk2=7.0;	                  
l1=50/13.5   ;	  % Wysunąć, kadłuby						
l2=25/13.5   ;	  % Przesunięcie boczne
dt2=40/13.5   ;	  % Średnica taktyczna, kadłuby						
du2=30/13.5  ;	  % Średnica ustalona, kadłuby	
% Dani ze stana statku.						
% Wyporności, mt.
% ładunkiem (eks)	Balastowy	Eksperyment
  D=22.9344 ;	    Db=7.333;	 De=22.9344;
  T1=0.86;	        T1b=0.545;	 T1e=0.86;     % Zanurzenie Dziobem, м.	
  T2=0.86;	        T2b=0.5445;   T2e=0.86;	  % Zanurzenie na Rufie, м.	
  % Współczynnik pełnienia ramowego kadłuba (MD frame), bЕ
  MDfr= 0.83;  MDfr_b=0.83;  MDfr_e=0.83;
Tsr1=(T1e+T2e)/2;
Tsr2=(T1+T2)/2;
dT1=((T2b-T1b)/LPP)*180/pi; % kąt trymu w stopnie w stanie balastowym
dT2=((T2-T1)/LPP)*180/pi;   % kąt trymu w stopnie w stanie załadowania
c1=1-fr/(LPP*Tsr1);           % współczynnik kompletności PS w stanie balastowym
c2=1-fr/(LPP*Tsr2);           % współczynnik kompletności PS w stanie załadowania
% Przetwarzanie wyników eksperymentu w celu określenia charakterystyki cyrkulacji i oznaczania współczynników gl1, gl2, gDт, gDy.
% Stosunkowe wydłużenie steru jest obliczane według wzoru: Ha=h²/A																																																					
Ha=(h^2)/A;
% stosunkowy obszar obracającej się części trzonu steru w procentach od	obszaru zanurząnej części PS;																						
Ar1=(A/(LPP*Tsr1))*100;           																																		
Ar2=(A/(LPP*Tsr2))*100;
%czynnik steru i kadłuba uwzględnia różne cechy statku, wpływając w pewien sposób na zdolność skrętu statku i jest określany na podstawie wyrażenia::
F1=(LPP/B)*(c1^2)/sqrt(Ha+Ar1);
F2=(LPP/B)*(c2^2)/sqrt(Ha+Ar2);
% Obliczenie elementów cyrkulacji w stanie balastowym
Lb1=6.41*(F1/sqrt(delta1))+0.7*dT1-0.93;  % (kadł)
Lb2=5.84*(F1/sqrt(delta1))+0.68*dT1-2.15; % (kadł)
Dt1=11.75*(F1/sqrt(delta1))+1.35*dT1-3.9; % (kadł)
Du1=11.61*(F1/sqrt(delta1))+1.2*dT1-4.31; % (kadł)

% Obliczenie elementów cyrkulacji w stanie załadowania
L1=6.41*(F2/sqrt(delta1))+0.7*dT2-0.93;  % (kadł)
L2=5.84*(F2/sqrt(delta1))+0.68*dT2-2.15; % (kadł)
Dt2=11.75*(F2/sqrt(delta1))+1.35*dT2-3.9; % (kadł)
Du2=11.61*(F2/sqrt(delta1))+1.2*dT2-4.31; % (kadł)

%Współczynniki filtrowania wartości elementów cyrkulacji w stanie balastowym
glb1=lb1/Lb1;
glb2=lb2/Lb2;
gdt1=dt1/Dt1;
gdu1=du1/Du1;
%Współczynniki filtrowania wartości elementów cyrkulacji w stanie załadowania
gl1=l1/L1;
gl2=l2/L2;
gdt2=dt2/Dt2;
gdu2=du2/Du2;

Deltab=[8 10 15 20 25 30 35];
Delta=[5 10 15 20 25 30 35]; %macierz wychylenia stera
Deltamk=[1 5 10 10 10 10 15]
%Elementy cyrkulacji w stanie balastowym dla wszystkich wychylenia stera
L1b=(6.41*(F1./sqrt(Deltab))+0.7*dT1-0.93)*glb1*(LPP)
L2b=(5.84*(F1./sqrt(Deltamk))+0.68*dT1-2.15)*glb2*(LPP); % 
Dtb=(11.75*(F1./sqrt(Deltab))+1.35*dT1-3.9)*gdt1*(LPP); % 
Dub=(11.61*(F1./sqrt(Deltab))+1.2*dT1-4.31)*gdu1*(LPP); % 

%Elementy cyrkulacji w stanie załadowania dla wszystkich wychylenia stera
L1l=(6.41*(F2./sqrt(Delta))+0.7*dT2-0.93)*gl1*(LPP);  % 
L2l=(5.84*(F2./sqrt(Deltamk))+0.68*dT2-2.15)*gl2*(LPP); % 
Dtl=(11.75*(F2./sqrt(Delta))+1.35*dT2-3.9)*gdt2*(LPP); % 
Dul=(11.61*(F2./sqrt(Delta))+1.2*dT2-4.31)*gdu2*(LPP); % 

if abs(TC2-TC1)>180 && TC2-TC1<0
    Turn1=mod(TC2-TC1,360)
elseif abs(TC2-TC1)>180 && TC2-TC1>0
    Turn1=mod(360,TC2-TC1)
else 
    Turn1=abs(TC2-TC1)
end

if abs(TC3-TC2)>180 && TC3-TC2<0
    Turn2=mod(TC3-TC2,360)
elseif abs(TC3-TC2)>180 && TC3-TC2>0
    Turn2=mod(360,TC3-TC2)
else 
    Turn2=abs(TC3-TC2)
end


if abs(TC4-TC3)>180 && TC4-TC3<0
    Turn3=mod(TC4-TC3,360)
elseif abs(TC4-TC3)>180 && TC4-TC3>0
    Turn3=mod(360,TC4-TC3)
else 
    Turn3=abs(TC4-TC3)
end

dTn1=Turn1/2;
dTn2=Turn2/2;
dTn3=Turn3/2;

HM1b=(L1b-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1b=L2b*tan(dTn1*pi/180);
HM2b=(L1b-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2b=L2b*tan(dTn2*pi/180);
HM3b=(L1b-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3b=L2b*tan(dTn3*pi/180);

HM1l=(L1l-Dtb/2+Dtb/2*tan(dTn1*pi/180));
MK1l=L2l*tan(dTn1*pi/180);
HM2l=(L1l-Dtb/2+Dtb/2*tan(dTn2*pi/180));
MK2l=L2l*tan(dTn2*pi/180);
HM3l=(L1l-Dtb/2+Dtb/2*tan(dTn3*pi/180));
MK3l=L2l*tan(dTn3*pi/180);
     
    LATHb1=LatM2+HM1b*cos((TC1+180)*pi/180)
    LONGHb1=LongM2+HM1b*sin((TC1+180)*pi/180)
    LATHb2=LatM3+HM2b*cos((TC2+180)*pi/180)
    LONGHb2=LongM3+HM2b*sin((TC2+180)*pi/180)
    LATHb3=LatM4+HM3b*cos((TC3+180)*pi/180)
    LONGHb3=LongM4+HM3b*sin((TC3+180)*pi/180)
    
    LATHl1=LatM2+HM1l*cos((TC1+180)*pi/180)
    LONGHl1=LongM2+HM1l*sin((TC1+180)*pi/180)
    LATHl2=LatM3+HM2l*cos((TC2+180)*pi/180)
    LONGHl2=LongM3+HM2l*sin((TC2+180)*pi/180)
    LATHl3=LatM4+HM3l*cos((TC3+180)*pi/180)
    LONGHl3=LongM4+HM3l*sin((TC3+180)*pi/180)
    
    LATKb1=LatM2+MK1b*cos((TC2)*pi/180)
    LONGKb1=LongM2+MK1b*sin((TC2)*pi/180) 
    LATKb2=LatM3+MK2b*cos((TC3)*pi/180)
    LONGKb2=LongM3+MK2b*sin((TC3)*pi/180)
    LATKb3=LatM4+MK3b*cos((TC4)*pi/180)
    LONGKb3=LongM4+MK3b*sin((TC4)*pi/180)
    
    
    LATKl1=LatM2+MK1l*cos((TC2)*pi/180)
    LONGKl1=LongM2+MK1l*sin((TC2)*pi/180) 
    LATKl2=LatM3+MK2l*cos((TC3)*pi/180)
    LONGKl2=LongM3+MK2l*sin((TC3)*pi/180)
    LATKl3=LatM4+MK3l*cos((TC4)*pi/180)
    LONGKl3=LongM4+MK3l*sin((TC4)*pi/180)
    
    
    TA=1 %Turning ability (1 is High, 2 is Middle, 3 is Low)
    Cond=1 %Condition(1-Ballast condition, 2-Load condition)
    if Cond==1 && TA==1 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatK1=LATKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatK1=LATKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatK1=LATKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatK1=LATKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatK1=LATKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatK1=LATKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatK1=LATKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatK1=LATKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatK1=LATKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatK1=LATKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatK1=LATKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatK1=LATKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatK1=LATKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatK1=LATKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatK1=LATKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatK1=LATKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatK1=LATKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatK1=LATKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatK1=LATKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatK1=LATKl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=20
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongK1=LONGKb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongK1=LONGKb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongK1=LONGKb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongK1=LONGKb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongK1=LONGKb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongK1=LONGKb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongK1=LONGKb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongK1=LONGKb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongK1=LONGKb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongK1=LONGKb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongK1=LONGKl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongK1=LONGKl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongK1=LONGKl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongK1=LONGKl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongK1=LONGKl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongK1=LONGKl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongK1=LONGKl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongK1=LONGKl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongK1=LONGKl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongK1=LONGKl1(1,7)    
    end 
   
    if Cond==1 && TA==1 && Turn1<=10
        LatH1=LATHb1(1,1) 
    elseif Cond==1 && TA==1 && Turn1<=30
        LatH1=LATHb1(1,2)  
    elseif Cond==1 && TA==1 && Turn1<=40
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LatH1=LATHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LatH1=LATHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LatH1=LATHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LatH1=LATHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LatH1=LATHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LatH1=LATHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LatH1=LATHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LatH1=LATHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LatH1=LATHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LatH1=LATHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LatH1=LATHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LatH1=LATHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LatH1=LATHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LatH1=LATHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LatH1=LATHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LatH1=LATHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LatH1=LATHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LatH1=LATHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LatH1=LATHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LatH1=LATHl1(1,7)    
    end  
        
    if Cond==1 && TA==1 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==1 && Turn1<=30
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==1 && Turn1<=40
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==1 && Turn1<=50
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==1 && Turn1<=55
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==1 && Turn1<=60
        LongH1=LONGHb1(1,6) 
    elseif Cond==1 && TA==1 && Turn1>60
        LongH1=LONGHb1(1,7)     
    elseif Cond==1 && TA==2 && Turn1<=10
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==2 && Turn1<=20
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==2 && Turn1<=30
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==2 && Turn1<=40
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==2 && Turn1<=45
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==2 && Turn1<=55
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==2 && Turn1>55
        LongH1=LONGHb1(1,7) 
    elseif Cond==1 && TA==3 && Turn1<=5
        LongH1=LONGHb1(1,1)
    elseif Cond==1 && TA==3 && Turn1<=10
        LongH1=LONGHb1(1,2)
    elseif Cond==1 && TA==3 && Turn1<=20
        LongH1=LONGHb1(1,3) 
    elseif Cond==1 && TA==3 && Turn1<=30
        LongH1=LONGHb1(1,4)  
    elseif Cond==1 && TA==3 && Turn1<=40
        LongH1=LONGHb1(1,5)     
    elseif Cond==1 && TA==3 && Turn1<=45
        LongH1=LONGHb1(1,6)
    elseif Cond==1 && TA==3 && Turn1>45
        LongH1=LONGHb1(1,7)  
    elseif Cond==2 && TA==1 && Turn1<=20
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==1 && Turn1<=30
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==1 && Turn1<=40
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==1 && Turn1<=50
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==1 && Turn1<=55
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==1 && Turn1<=60
        LongH1=LONGHl1(1,6) 
    elseif Cond==2 && TA==1 && Turn1>60
        LongH1=LONGHl1(1,7)     
    elseif Cond==2 && TA==2 && Turn1<=10
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==2 && Turn1<=20
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==2 && Turn1<=30
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==2 && Turn1<=40
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==2 && Turn1<=45
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==2 && Turn1<=55
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==2 && Turn1>55
        LongH1=LONGHl1(1,7) 
    elseif Cond==2 && TA==3 && Turn1<=5
        LongH1=LONGHl1(1,1)
    elseif Cond==2 && TA==3 && Turn1<=10
        LongH1=LONGHl1(1,2)
    elseif Cond==2 && TA==3 && Turn1<=20
        LongH1=LONGHl1(1,3) 
    elseif Cond==2 && TA==3 && Turn1<=30
        LongH1=LONGHl1(1,4)  
    elseif Cond==2 && TA==3 && Turn1<=40
        LongH1=LONGHl1(1,5)     
    elseif Cond==2 && TA==3 && Turn1<=45
        LongH1=LONGHl1(1,6)
    elseif Cond==2 && TA==3 && Turn1>45
        LongH1=LONGHl1(1,7)    
    end 
    
    if Cond==1 && TA==1 && Turn2<=20
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatH2=LATHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatH2=LATHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatH2=LATHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatH2=LATHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatH2=LATHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatH2=LATHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatH2=LATHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatH2=LATHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatH2=LATHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatH2=LATHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatH2=LATHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatH2=LATHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatH2=LATHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatH2=LATHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatH2=LATHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatH2=LATHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatH2=LATHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatH2=LATHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatH2=LATHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatH2=LATHl2(1,7)  
    else
        LatH2=LatK1
    end  
        
    if Cond==1 && TA==1 && Turn2<=20
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongH2=LONGHb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongH2=LONGHb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongH2=LONGHb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongH2=LONGHb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongH2=LONGHb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongH2=LONGHb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongH2=LONGHb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongH2=LONGHb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongH2=LONGHb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongH2=LONGHb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongH2=LONGHl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongH2=LONGHl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongH2=LONGHl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongH2=LONGHl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongH2=LONGHl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongH2=LONGHl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongH2=LONGHl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongH2=LONGHl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongH2=LONGHl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongH2=LONGHl2(1,7)    
    else
        LongH2=LongK1
    end
       if Cond==1 && TA==1 && Turn2<=20
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LatK2=LATKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LatK2=LATKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LatK2=LATKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LatK2=LATKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LatK2=LATKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LatK2=LATKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LatK2=LATKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LatK2=LATKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LatK2=LATKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LatK2=LATKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LatK2=LATKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LatK2=LATKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LatK2=LATKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LatK2=LATKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LatK2=LATKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LatK2=LATKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LatK2=LATKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LatK2=LATKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LatK2=LATKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LatK2=LATKl2(1,7)  
       else
           LatK2=LatK1
       end  
       if Cond==1 && TA==1 && Turn2<=20
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==1 && Turn2<=30
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==1 && Turn2<=40
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==1 && Turn2<=50
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==1 && Turn2<=55
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==1 && Turn2<=60
        LongK2=LONGKb2(1,6) 
    elseif Cond==1 && TA==1 && Turn2>60
        LongK2=LONGKb2(1,7)     
    elseif Cond==1 && TA==2 && Turn2<=10
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==2 && Turn2<=20
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==2 && Turn2<=30
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==2 && Turn2<=40
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==2 && Turn2<=45
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==2 && Turn2<=55
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==2 && Turn2>55
        LongK2=LONGKb2(1,7) 
    elseif Cond==1 && TA==3 && Turn2<=5
        LongK2=LONGKb2(1,1)
    elseif Cond==1 && TA==3 && Turn2<=10
        LongK2=LONGKb2(1,2)
    elseif Cond==1 && TA==3 && Turn2<=20
        LongK2=LONGKb2(1,3) 
    elseif Cond==1 && TA==3 && Turn2<=30
        LongK2=LONGKb2(1,4)  
    elseif Cond==1 && TA==3 && Turn2<=40
        LongK2=LONGKb2(1,5)     
    elseif Cond==1 && TA==3 && Turn2<=45
        LongK2=LONGKb2(1,6)
    elseif Cond==1 && TA==3 && Turn2>45
        LongK2=LONGKb2(1,7)  
    elseif Cond==2 && TA==1 && Turn2<=20
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==1 && Turn2<=30
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==1 && Turn2<=40
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==1 && Turn2<=50
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==1 && Turn2<=55
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==1 && Turn2<=60
        LongK2=LONGKl2(1,6) 
    elseif Cond==2 && TA==1 && Turn2>60
        LongK2=LONGKl2(1,7)     
    elseif Cond==2 && TA==2 && Turn2<=10
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==2 && Turn2<=20
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==2 && Turn2<=30
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==2 && Turn2<=40
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==2 && Turn2<=45
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==2 && Turn2<=55
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==2 && Turn2>55
        LongK2=LONGKl2(1,7) 
    elseif Cond==2 && TA==3 && Turn2<=5
        LongK2=LONGKl2(1,1)
    elseif Cond==2 && TA==3 && Turn2<=10
        LongK2=LONGKl2(1,2)
    elseif Cond==2 && TA==3 && Turn2<=20
        LongK2=LONGKl2(1,3) 
    elseif Cond==2 && TA==3 && Turn2<=30
        LongK2=LONGKl2(1,4)  
    elseif Cond==2 && TA==3 && Turn2<=40
        LongK2=LONGKl2(1,5)     
    elseif Cond==2 && TA==3 && Turn2<=45
        LongK2=LONGKl2(1,6)
    elseif Cond==2 && TA==3 && Turn2>45
        LongK2=LONGKl2(1,7) 
       else
        LongK2=LongK1
    end
    if Cond==1 && TA==1 && Turn3<=20
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatH3=LATHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatH3=LATHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatH3=LATHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatH3=LATHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatH3=LATHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatH3=LATHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatH3=LATHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatH3=LATHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatH3=LATHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatH3=LATHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatH3=LATHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatH3=LATHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatH3=LATHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatH3=LATHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatH3=LATHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatH3=LATHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatH3=LATHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatH3=LATHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatH3=LATHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatH3=LATHl3(1,7) 
    else
        LatH3=LatH2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongH3=LONGHb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongH3=LONGHb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongH3=LONGHb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongH3=LONGHb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongH3=LONGHb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongH3=LONGHb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongH3=LONGHb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongH3=LONGHb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongH3=LONGHb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongH3=LONGHb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongH3=LONGHl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongH3=LONGHl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongH3=LONGHl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongH3=LONGHl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongH3=LONGHl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongH3=LONGHl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongH3=LONGHl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongH3=LONGHl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongH3=LONGHl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongH3=LONGHl3(1,7)
    else
        LongH3=LongK2
    end
    
    
    
    if Cond==1 && TA==1 && Turn3<=20
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LatK3=LATKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LatK3=LATKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LatK3=LATKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LatK3=LATKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LatK3=LATKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LatK3=LATKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LatK3=LATKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LatK3=LATKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LatK3=LATKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LatK3=LATKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LatK3=LATKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LatK3=LATKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LatK3=LATKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LatK3=LATKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LatK3=LATKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LatK3=LATKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LatK3=LATKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LatK3=LATKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LatK3=LATKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LatK3=LATKl3(1,7)  
    else
        LatK3=LatK2
    end  
        
    if Cond==1 && TA==1 && Turn3<=20
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==1 && Turn3<=30
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==1 && Turn3<=40
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==1 && Turn3<=50
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==1 && Turn3<=55
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==1 && Turn3<=60
        LongK3=LONGKb3(1,6) 
    elseif Cond==1 && TA==1 && Turn3>60
        LongK3=LONGKb3(1,7)     
    elseif Cond==1 && TA==2 && Turn3<=10
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==2 && Turn3<=20
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==2 && Turn3<=30
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==2 && Turn3<=40
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==2 && Turn3<=45
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==2 && Turn3<=55
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==2 && Turn3>55
        LongK3=LONGKb3(1,7) 
    elseif Cond==1 && TA==3 && Turn3<=5
        LongK3=LONGKb3(1,1)
    elseif Cond==1 && TA==3 && Turn3<=10
        LongK3=LONGKb3(1,2)
    elseif Cond==1 && TA==3 && Turn3<=20
        LongK3=LONGKb3(1,3) 
    elseif Cond==1 && TA==3 && Turn3<=30
        LongK3=LONGKb3(1,4)  
    elseif Cond==1 && TA==3 && Turn3<=40
        LongK3=LONGKb3(1,5)     
    elseif Cond==1 && TA==3 && Turn3<=45
        LongK3=LONGKb3(1,6)
    elseif Cond==1 && TA==3 && Turn3>45
        LongK3=LONGKb3(1,7)  
    elseif Cond==2 && TA==1 && Turn3<=20
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==1 && Turn3<=30
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==1 && Turn3<=40
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==1 && Turn3<=50
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==1 && Turn3<=55
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==1 && Turn3<=60
        LongK3=LONGKl3(1,6) 
    elseif Cond==2 && TA==1 && Turn3>60
        LongK3=LONGKl3(1,7)     
    elseif Cond==2 && TA==2 && Turn3<=10
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==2 && Turn3<=20
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==2 && Turn3<=30
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==2 && Turn3<=40
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==2 && Turn3<=45
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==2 && Turn3<=55
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==2 && Turn3>55
        LongK3=LONGKl3(1,7) 
    elseif Cond==2 && TA==3 && Turn3<=5
        LongK3=LONGKl3(1,1)
    elseif Cond==2 && TA==3 && Turn3<=10
        LongK3=LONGKl3(1,2)
    elseif Cond==2 && TA==3 && Turn3<=20
        LongK3=LONGKl3(1,3) 
    elseif Cond==2 && TA==3 && Turn3<=30
        LongK3=LONGKl3(1,4)  
    elseif Cond==2 && TA==3 && Turn3<=40
        LongK3=LONGKl3(1,5)     
    elseif Cond==2 && TA==3 && Turn3<=45
        LongK3=LONGKl3(1,6)
    elseif Cond==2 && TA==3 && Turn3>45
        LongK3=LONGKl3(1,7)    
    else 
        LongK3=LongK2
    end
    Emp=[]; 
     
     %y3=[LatM1 LatH1 LatM2 LatK1 LatH2 LatM3 LatK2 LatH3 LatM4 LatK3 LatM5]
     %x3=[LongM1 LongH1 LongM2 LongK1 LongH2 LongM3 LongK2 LongH3 LongM4 LongK3 LongM5] 
%     %plot(x3,y3)
    % Turn1
    psi=2; %step
       
    if  TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)<TC2
    Turning1=[TC1:psi:360, 0:psi:TC2-(1/3)*Turn1]
    elseif TC1>=270 && TC2<=90 && mod(TC2,(1/3)*Turn1)==TC2
    Turning1=[TC1:psi:360-((1/3)*Turn1-mod(TC2,(1/3)*Turn1))]
    elseif TC2-TC1<180 && TC2-TC1>0
    Turning1=[TC1:psi:TC2-(1/3)*Turn1]
    else
    Turning1=[TC1:-psi:TC1-(2/3)*Turn1]  
    end
    step1=(Turning1(1,length(unique(Turning1)))-Turning1(1,1))/(length(unique(Turning1))-1);
    
    if TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)<TC3
    Turning2=[TC2:psi:360, 0:psi:TC3-(1/3)*Turn2]
    elseif TC2>=270 && TC3<=90 && mod(TC3,(1/3)*Turn2)==TC3
    Turning2=[TC2:psi:360-((1/3)*Turn2-mod(TC3,(1/3)*Turn2))]
    elseif TC3-TC2<180 && TC3-TC2>0
    Turning2=[TC2:psi:TC3-(1/3)*Turn2]
    else
    Turning2=[TC2:-psi:TC2-(2/3)*Turn2]  
    end
    step2=(Turning2(1,length(unique(Turning2)))-Turning2(1,1))/(length(unique(Turning2))-1);
   
    if  TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)<TC4
    Turning3=[TC3:psi:360, 0:psi:TC4-(1/3)*Turn3]
    elseif TC3>=270 && TC4<=90 && mod(TC4,(1/3)*Turn3)==TC4
    Turning3=[TC3:psi:360-((1/3)*Turn3-mod(TC4,(1/3)*Turn3))]
    elseif TC4-TC3<180 && TC4-TC3>0
    Turning3=[TC3:psi:TC4-(1/3)*Turn3]
    else
    Turning3=[TC3:-psi:TC3-(2/3)*Turn3]
    end
    step3=(Turning3(1,length(unique(Turning3)))-Turning3(1,1))/(length(unique(Turning3))-1);
length(unique(Turning1)); 
length(unique(Turning2));
length(unique(Turning3));

dpsi=360/psi;
kdib=[0.80 1.00 1.25 1.44 1.80 2.00 2.10];
kdil=[0.98 1.20 1.30 1.70 1.95 2.20 2.35]; %first coefficient
 if TA==1 && Turn1<=10
        Delta1=Delta(1,1) 
 elseif TA==1 && Turn1<=30
        Delta1=Delta(1,2)   
 elseif TA==1 && Turn1<=40
        Delta1=Delta(1,3) 
 elseif TA==1 && Turn1<=50
        Delta1=Delta(1,4)  
 elseif TA==1 && Turn1<=55
        Delta1=Delta(1,5)     
 elseif TA==1 && Turn1<=60
        Delta1=Delta(1,6)
 elseif TA==1 && Turn1>60
        Delta1=Delta(1,7)     
 elseif TA==2 && Turn1<=10
        Delta1=Delta(1,1)
 elseif TA==2 && Turn1<=20
        Delta1=Delta(1,2)
 elseif TA==2 && Turn1<=30
        Delta1=Delta(1,3) 
 elseif TA==2 && Turn1<=40
        Delta1=Delta(1,4)  
 elseif TA==2 && Turn1<=45
        Delta1=Delta(1,5)     
 elseif TA==2 && Turn1<=55
        Delta1=Delta(1,6)
 elseif TA==2 && Turn1>55
        Delta1=Delta(1,7) 
 elseif TA==3 && Turn1<=5
        Delta1=Delta(1,1)
 elseif TA==3 && Turn1<=10
        Delta1=Delta(1,2)
 elseif TA==3 && Turn1<=20
        Delta1=Delta(1,3) 
 elseif TA==3 && Turn1<=30
        Delta1=Delta(1,4)  
 elseif TA==3 && Turn1<=40
        Delta1=Delta(1,5)     
 elseif TA==3 && Turn1<=45
        Delta1=Delta(1,6)
 elseif TA==3 && Turn1>45
        Delta1=Delta(1,7) 
 end

if Turn1<=90 && Cond==1
do1=((11.75*(F1./sqrt(Delta1))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn1<=90 && Cond==2
do1=((11.75*(F2./sqrt(Delta1))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do1=((11.61*(F1/sqrt(Delta1))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do1=((11.61*(F2/sqrt(Delta1))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end 

 if Cond==1 && Delta1==Delta(1,1) 
    kdi1=kdib(1,1)
 elseif Cond==1 && Delta1==Delta(1,2) 
    kdi1=kdib(1,2)  
 elseif Cond==1 && Delta1==Delta(1,3) 
    kdi1=kdib(1,3)
 elseif Cond==1 && Delta1==Delta(1,4) 
    kdi1=kdib(1,4)
 elseif Cond==1 && Delta1==Delta(1,5) 
    kdi1=kdib(1,5)    
 elseif Cond==1 && Delta1==Delta(1,6) 
    kdi1=kdib(1,6)
 elseif Cond==1 && Delta1==Delta(1,7) 
    kdi1=kdib(1,7)    
 elseif Cond==2 && Delta1==Delta(1,1) 
    kdi1=kdil(1,1)
 elseif Cond==2 && Delta1==Delta(1,2) 
    kdi1=kdil(1,2)  
 elseif Cond==2 && Delta1==Delta(1,3) 
    kdi1=kdil(1,3)
 elseif Cond==2 && Delta1==Delta(1,4) 
    kdi1=kdil(1,4)
 elseif Cond==2 && Delta1==Delta(1,5) 
    kdi1=kdil(1,5)    
 elseif Cond==2 && Delta1==Delta(1,6) 
    kdi1=kdil(1,6)
 elseif Cond==2 && Delta1==Delta(1,7) 
    kdi1=kdil(1,7)    
    end

if Turn1>60
    kt1=0.8
else
    kt1=1
end
if Turn1<25
    kt21=0.3
else
    kt21=1
end
if Cond==1 && Delta1<=15
    Kh1=2.01
elseif Cond==1 && Delta1>=20
    Kh1=1.35
elseif Cond==2 && Delta1<=15
    Kh1=6.7
elseif Cond==2 && Delta1>=20
    Kh1=4.5
end
if D2<=3.5*LOA && sign(step1)==sign(step2)
kdt1=0.3
else
kdt1=1
end
p1=2
if p1<length(unique(Turning1))
a1=Turning1(1,p1)
else
a1=Emp
end
LAThi1=LatH1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a1*pi/180)
LONGhi1=LongH1+ Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a1*pi/180)     
if p1+1<=length(unique(Turning1)) && Turn1>4 a2=Turning1(1,p1+1)
else a2=Emp
end
LAThi2=LAThi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*cos(a2*pi/180)
LONGhi2=LONGhi1 + Kh1*kdt1*kt21*kt1*kdi1*do1*sin(a2*pi/180)     
if p1+2<=length(unique(Turning1)) a3=Turning1(1,p1+2)
else a3=Emp
end
LAThi3=LAThi2 + kt1*kdi1*do1*cos(a3*pi/180)
LONGhi3=LONGhi2 + kt1*kdi1*do1*sin(a3*pi/180)     
if p1+3<=length(unique(Turning1)) a4=Turning1(1,p1+3) 
else a4=Emp; 
end
LAThi4=LAThi3 + kt1*kdi1*do1*cos(a4*pi/180);
LONGhi4=LONGhi3 + kt1*kdi1*do1*sin(a4*pi/180)     
if  p1+4<=length(unique(Turning1)) a5=Turning1(1,p1+4) 
else a5=Emp 
end
LAThi5=LAThi4 + kt1*kdi1*do1*cos(a5*pi/180)
LONGhi5=LONGhi4 + kt1*kdi1*do1*sin(a5*pi/180)     
if p1+5<=length(unique(Turning1)) a6=Turning1(1,p1+5) 
else a6=Emp 
end
LAThi6=LAThi5 + kt1*kdi1*do1*cos(a6*pi/180)
LONGhi6=LONGhi5 + kt1*kdi1*do1*sin(a6*pi/180)     
if p1+6<=length(unique(Turning1)) a7=Turning1(1,p1+6) 
else a7=Emp 
end
LAThi7=LAThi6 + kt1*kdi1*do1*cos(a7*pi/180)
LONGhi7=LONGhi6 + kt1*kdi1*do1*sin(a7*pi/180)     
if p1+7<=length(unique(Turning1)) a8=Turning1(1,p1+7) 
else a8=Emp 
end
LAThi8=LAThi7 + kt1*kdi1*do1*cos(a8*pi/180)
LONGhi8=LONGhi7 + kt1*kdi1*do1*sin(a8*pi/180)     
if  p1+8<=length(unique(Turning1)) a9=Turning1(1,p1+8) 
else a9=Emp 
end
LAThi9=LAThi8 + kt1*kdi1*do1*cos(a9*pi/180)
LONGhi9=LONGhi8 + kt1*kdi1*do1*sin(a9*pi/180)     
if p1+9<=length(unique(Turning1)) a10=Turning1(1,p1+9) 
else a10=Emp 
end
LAThi10=LAThi9 + kt1*kdi1*do1*cos(a10*pi/180)
LONGhi10=LONGhi9 + kt1*kdi1*do1*sin(a10*pi/180)     
if p1+10<=length(unique(Turning1)) a11=Turning1(1,p1+10) 
else a11=Emp 
end
LAThi11=LAThi10 + kt1*kdi1*do1*cos(a11*pi/180)
LONGhi11=LONGhi10 + kt1*kdi1*do1*sin(a11*pi/180)     
if p1+11<=length(unique(Turning1)) a12=Turning1(1,p1+11) 
else a12=Emp 
end
LAThi12=LAThi11 + kt1*kdi1*do1*cos(a12*pi/180)
LONGhi12=LONGhi11 + kt1*kdi1*do1*sin(a12*pi/180)     
if p1+12<=length(unique(Turning1)) a13=Turning1(1,p1+12) 
else a13=Emp 
end
LAThi13=LAThi12 + kt1*kdi1*do1*cos(a13*pi/180)
LONGhi13=LONGhi12 + kt1*kdi1*do1*sin(a13*pi/180)     
if p1+13<=length(unique(Turning1)) a14=Turning1(1,p1+13) 
else a14=Emp 
end
LAThi14=LAThi13 + kt1*kdi1*do1*cos(a14*pi/180)
LONGhi14=LONGhi13 + kt1*kdi1*do1*sin(a14*pi/180)     
if p1+14<=length(unique(Turning1)) a15=Turning1(1,p1+14) 
else a15=Emp 
end
LAThi15=LAThi14 + kt1*kdi1*do1*cos(a15*pi/180)
LONGhi15=LONGhi14 + kt1*kdi1*do1*sin(a15*pi/180)     
if p1+15<=length(unique(Turning1)) a16=Turning1(1,p1+15) 
else a16=Emp 
end
LAThi16=LAThi15 + kt1*kdi1*do1*cos(a16*pi/180)
LONGhi16=LONGhi15 + kt1*kdi1*do1*sin(a16*pi/180)     
if p1+16<=length(unique(Turning1)) a17=Turning1(1,p1+16) 
else a17=Emp 
end
LAThi17=LAThi16 + kt1*kdi1*do1*cos(a17*pi/180)
LONGhi17=LONGhi16 + kt1*kdi1*do1*sin(a17*pi/180)     
if p1+17<=length(unique(Turning1))  a18=Turning1(1,p1+17) 
else a18=Emp 
end
LAThi18=LAThi17 + kt1*kdi1*do1*cos(a18*pi/180)
LONGhi18=LONGhi17 + kt1*kdi1*do1*sin(a18*pi/180)     
if p1+18<=length(unique(Turning1)) a19=Turning1(1,p1+18) 
else a19=Emp 
end
LAThi19=LAThi18 + kt1*kdi1*do1*cos(a19*pi/180)
LONGhi19=LONGhi18 + kt1*kdi1*do1*sin(a19*pi/180)     
if p1+19<=length(unique(Turning1)) a20=Turning1(1,p1+19) 
else a20=Emp 
end
LAThi20=LAThi19 + kt1*kdi1*do1*cos(a20*pi/180)
LONGhi20=LONGhi19 + kt1*kdi1*do1*sin(a20*pi/180)     
if p1+20<=length(unique(Turning1)) a21=Turning1(1,p1+20) 
else a21=Emp 
end
LAThi21=LAThi20 + kt1*kdi1*do1*cos(a21*pi/180)
LONGhi21=LONGhi20 + kt1*kdi1*do1*sin(a21*pi/180)     
if p1+21<=length(unique(Turning1)) a22=Turning1(1,p1+21) 
else a22=Emp 
end
LAThi22=LAThi21 + kt1*kdi1*do1*cos(a22*pi/180)
LONGhi22=LONGhi21 + kt1*kdi1*do1*sin(a22*pi/180)     
if p1+22<=length(unique(Turning1)) a23=Turning1(1,p1+22) 
else a23=Emp 
end
LAThi23=LAThi22 + kt1*kdi1*do1*cos(a23*pi/180)
LONGhi23=LONGhi22 + kt1*kdi1*do1*sin(a23*pi/180)     
if p1+23<=length(unique(Turning1)) a24=Turning1(1,p1+23) 
else a24=Emp 
end
LAThi24=LAThi23 + kt1*kdi1*do1*cos(a24*pi/180)
LONGhi24=LONGhi23 + kt1*kdi1*do1*sin(a24*pi/180)     
if p1+24<=length(unique(Turning1)) a25=Turning1(1,p1+24) 
else a25=Emp 
end 
LAThi25=LAThi24 + kt1*kdi1*do1*cos(a25*pi/180)
LONGhi25=LONGhi24 + kt1*kdi1*do1*sin(a25*pi/180)     
if p1+25<=length(unique(Turning1)) a26=Turning1(1,p1+25) 
else a26=Emp 
end 
LAThi26=LAThi25 + kt1*kdi1*do1*cos(a26*pi/180)
LONGhi26=LONGhi25 + kt1*kdi1*do1*sin(a26*pi/180)     
if p1+26<=length(unique(Turning1)) a27=Turning1(1,p1+26) 
else a27=Emp 
end 
LAThi27=LAThi26 + kt1*kdi1*do1*cos(a27*pi/180)
LONGhi27=LONGhi26 + kt1*kdi1*do1*sin(a27*pi/180)     
if p1+27<=length(unique(Turning1)) a28=Turning1(1,p1+27) 
else a28=Emp 
end 
LAThi28=LAThi27 + kt1*kdi1*do1*cos(a28*pi/180)
LONGhi28=LONGhi27 + kt1*kdi1*do1*sin(a28*pi/180)     
if p1+28<=length(unique(Turning1)) a29=Turning1(1,p1+28) 
else a29=Emp 
end 
LAThi29=LAThi28 + kt1*kdi1*do1*cos(a29*pi/180)
LONGhi29=LONGhi28 + kt1*kdi1*do1*sin(a29*pi/180)     
if p1+29<=length(unique(Turning1)) a30=Turning1(1,p1+29) 
else a30=Emp 
end 
LAThi30=LAThi29 + kt1*kdi1*do1*cos(a30*pi/180)
LONGhi30=LONGhi29 + kt1*kdi1*do1*sin(a30*pi/180)     
if p1+30<=length(unique(Turning1)) a31=Turning1(1,p1+30) 
else a31=Emp 
end 
LAThi31=LAThi30 + kt1*kdi1*do1*cos(a31*pi/180)
LONGhi31=LONGhi30 + kt1*kdi1*do1*sin(a31*pi/180)     
if p1+31<=length(unique(Turning1)) a32=Turning1(1,p1+31) 
else a32=Emp 
end 
LAThi32=LAThi31 + kt1*kdi1*do1*cos(a32*pi/180)
LONGhi32=LONGhi31 + kt1*kdi1*do1*sin(a32*pi/180)     
if p1+32<=length(unique(Turning1)) a33=Turning1(1,p1+32)
else a33=Emp
end
LAThi33=LAThi32 + kt1*kdi1*do1*cos(a33*pi/180)
LONGhi33=LONGhi32 + kt1*kdi1*do1*sin(a33*pi/180)     
if p1+33<=length(unique(Turning1)) a34=Turning1(1,p1+33) 
else a34=Emp 
end
LAThi34=LAThi33 + kt1*kdi1*do1*cos(a34*pi/180)
LONGhi34=LONGhi33 + kt1*kdi1*do1*sin(a34*pi/180)     
if p1+34<=length(unique(Turning1)) a35=Turning1(1,p1+34) 
else a35=Emp 
end
LAThi35=LAThi34 + kt1*kdi1*do1*cos(a35*pi/180)
LONGhi35=LONGhi34 + kt1*kdi1*do1*sin(a35*pi/180)     
if p1+35<=length(unique(Turning1)) a36=Turning1(1,p1+35) 
else a36=Emp 
end
LAThi36=LAThi35 + kt1*kdi1*do1*cos(a36*pi/180)
LONGhi36=LONGhi35 + kt1*kdi1*do1*sin(a36*pi/180)     
if p1+36<=length(unique(Turning1)) a37=Turning1(1,p1+36) 
else a37=Emp 
end
LAThi37=LAThi36 + kt1*kdi1*do1*cos(a37*pi/180)
LONGhi37=LONGhi36 + kt1*kdi1*do1*sin(a37*pi/180)     
if p1+37<=length(unique(Turning1)) a38=Turning1(1,p1+37) 
else a38=Emp 
end
LAThi38=LAThi37 + kt1*kdi1*do1*cos(a38*pi/180)
LONGhi38=LONGhi37 + kt1*kdi1*do1*sin(a38*pi/180)     
if p1+38<=length(unique(Turning1)) a39=Turning1(1,p1+38) 
else a39=Emp 
end
LAThi39=LAThi38 + kt1*kdi1*do1*cos(a39*pi/180)
LONGhi39=LONGhi38 + kt1*kdi1*do1*sin(a39*pi/180)     
if p1+39<=length(unique(Turning1)) a40=Turning1(1,p1+39) 
else a40=Emp 
end
LAThi40=LAThi39 + kt1*kdi1*do1*cos(a40*pi/180)
LONGhi40=LONGhi39 + kt1*kdi1*do1*sin(a40*pi/180)     
if p1+40<=length(unique(Turning1)) a41=Turning1(1,p1+40) 
else a41=Emp 
end
LAThi41=LAThi40 + kt1*kdi1*do1*cos(a41*pi/180)
LONGhi41=LONGhi40 + kt1*kdi1*do1*sin(a41*pi/180)     
if p1+41<=length(unique(Turning1)) a42=Turning1(1,p1+41) 
else a42=Emp 
end
LAThi42=LAThi41 + kt1*kdi1*do1*cos(a42*pi/180)
LONGhi42=LONGhi41 + kt1*kdi1*do1*sin(a42*pi/180)     
if p1+42<=length(unique(Turning1)) a43=Turning1(1,p1+42) 
else a43=Emp 
end
LAThi43=LAThi42 + kt1*kdi1*do1*cos(a43*pi/180)
LONGhi43=LONGhi42 + kt1*kdi1*do1*sin(a43*pi/180)     
if p1+43<=length(unique(Turning1)) a44=Turning1(1,p1+43) 
else a44=Emp 
end
LAThi44=LAThi43 + kt1*kdi1*do1*cos(a44*pi/180)
LONGhi44=LONGhi43 + kt1*kdi1*do1*sin(a44*pi/180)     
if p1+44<=length(unique(Turning1)) a45=Turning1(1,p1+44) 
else a45=Emp 
end
LAThi45=LAThi44 + kt1*kdi1*do1*cos(a45*pi/180)
LONGhi45=LONGhi44 + kt1*kdi1*do1*sin(a45*pi/180)     
if p1+45<=length(unique(Turning1)) a46=Turning1(1,p1+45) 
else a46=Emp 
end
LAThi46=LAThi45 + kt1*kdi1*do1*cos(a46*pi/180)
LONGhi46=LONGhi45 + kt1*kdi1*do1*sin(a46*pi/180)     
if p1+46<=length(unique(Turning1)) a47=Turning1(1,p1+46) 
else a47=Emp 
end
LAThi47=LAThi46 + kt1*kdi1*do1*cos(a47*pi/180)
LONGhi47=LONGhi46 + kt1*kdi1*do1*sin(a47*pi/180)     
if p1+47<=length(unique(Turning1)) a48=Turning1(1,p1+47) 
else a48=Emp 
end
LAThi48=LAThi47 + kt1*kdi1*do1*cos(a48*pi/180)
LONGhi48=LONGhi47 + kt1*kdi1*do1*sin(a48*pi/180)     
if p1+48<=length(unique(Turning1)) a49=Turning1(1,p1+48) 
else a49=Emp 
end
LAThi49=LAThi48 + kt1*kdi1*do1*cos(a49*pi/180)
LONGhi49=LONGhi48 + kt1*kdi1*do1*sin(a49*pi/180)     
if p1+49<=length(unique(Turning1)) a50=Turning1(1,p1+49) 
else a50=Emp 
end
LAThi50=LAThi49 + kt1*kdi1*do1*cos(a50*pi/180)
LONGhi50=LONGhi49 + kt1*kdi1*do1*sin(a50*pi/180)     
if p1+50<=length(unique(Turning1)) a51=Turning1(1,p1+50) 
else a51=Emp 
end
LAThi51=LAThi50 + kt1*kdi1*do1*cos(a51*pi/180)
LONGhi51=LONGhi50 + kt1*kdi1*do1*sin(a51*pi/180)     
if p1+51<=length(unique(Turning1)) a52=Turning1(1,p1+51) 
else a52=Emp 
end
LAThi52=LAThi51 + kt1*kdi1*do1*cos(a52*pi/180)
LONGhi52=LONGhi51 + kt1*kdi1*do1*sin(a52*pi/180)     
if p1+52<=length(unique(Turning1)) a53=Turning1(1,p1+52) 
else a53=Emp 
end
LAThi53=LAThi52 + kt1*kdi1*do1*cos(a53*pi/180)
LONGhi53=LONGhi52 + kt1*kdi1*do1*sin(a53*pi/180)     
if p1+53<=length(unique(Turning1)) a54=Turning1(1,p1+53) 
else a54=Emp 
end
LAThi54=LAThi53 + kt1*kdi1*do1*cos(a54*pi/180)
LONGhi54=LONGhi53 + kt1*kdi1*do1*sin(a54*pi/180)     
if p1+54<=length(unique(Turning1)) a55=Turning1(1,p1+54) 
else a55=Emp 
end 
LAThi55=LAThi54 + kt1*kdi1*do1*cos(a55*pi/180)
LONGhi55=LONGhi54 + kt1*kdi1*do1*sin(a55*pi/180)     
if p1+55<=length(unique(Turning1)) a56=Turning1(1,p1+55) 
else a56=Emp 
end 
LAThi56=LAThi55 + kt1*kdi1*do1*cos(a56*pi/180)
LONGhi56=LONGhi55 + kt1*kdi1*do1*sin(a56*pi/180)     
if p1+56<=length(unique(Turning1)) a57=Turning1(1,p1+56) 
else a57=Emp 
end 
LAThi57=LAThi56 + kt1*kdi1*do1*cos(a57*pi/180)
LONGhi57=LONGhi56 + kt1*kdi1*do1*sin(a57*pi/180)     
if p1+57<=length(unique(Turning1)) a58=Turning1(1,p1+57) 
else a58=Emp 
end 
LAThi58=LAThi57 + kt1*kdi1*do1*cos(a58*pi/180)
LONGhi58=LONGhi57 + kt1*kdi1*do1*sin(a58*pi/180)     
if p1+58<=length(unique(Turning1)) a59=Turning1(1,p1+58) 
else a59=Emp 
end 
LAThi59=LAThi58 + kt1*kdi1*do1*cos(a59*pi/180)
LONGhi59=LONGhi58 + kt1*kdi1*do1*sin(a59*pi/180)     
if p1+59<=length(unique(Turning1)) a60=Turning1(1,p1+59) 
else a60=Emp 
end 
LAThi60=LAThi59 + kt1*kdi1*do1*cos(a60*pi/180)
LONGhi60=LONGhi59 + kt1*kdi1*do1*sin(a60*pi/180)                

digitsOld=digits(9)

if TA==1 && Turn2<=10
        Delta2=Delta(1,1) 
 elseif TA==1 && Turn2<=30
        Delta2=Delta(1,2)   
 elseif TA==1 && Turn2<=40
        Delta2=Delta(1,3) 
 elseif TA==1 && Turn2<=50
        Delta2=Delta(1,4)  
 elseif TA==1 && Turn2<=55
        Delta2=Delta(1,5)     
 elseif TA==1 && Turn2<=60
        Delta2=Delta(1,6)
 elseif TA==1 && Turn2>60
        Delta2=Delta(1,7)     
 elseif TA==2 && Turn2<=10
        Delta2=Delta(1,1)
 elseif TA==2 && Turn2<=20
        Delta2=Delta(1,2)
 elseif TA==2 && Turn2<=30
        Delta2=Delta(1,3) 
 elseif TA==2 && Turn2<=40
        Delta2=Delta(1,4)  
 elseif TA==2 && Turn2<=45
        Delta2=Delta(1,5)     
 elseif TA==2 && Turn2<=55
        Delta2=Delta(1,6)
 elseif TA==2 && Turn2>55
        Delta2=Delta(1,7) 
 elseif TA==3 && Turn2<=5
        Delta2=Delta(1,1)
 elseif TA==3 && Turn2<=10
        Delta2=Delta(1,2)
 elseif TA==3 && Turn2<=20
        Delta2=Delta(1,3) 
 elseif TA==3 && Turn2<=30
        Delta2=Delta(1,4)  
 elseif TA==3 && Turn2<=40
        Delta2=Delta(1,5)     
 elseif TA==3 && Turn2<=45
        Delta2=Delta(1,6)
 elseif TA==3 && Turn2>45
        Delta2=Delta(1,7)
  else    
        Delta2=0
 end

if Turn2<=90 && Cond==1
do2=((11.75*(F1./sqrt(Delta2))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn2<=90 && Cond==2
do2=((11.75*(F2./sqrt(Delta2))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do2=((11.61*(F1/sqrt(Delta2))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do2=((11.61*(F2/sqrt(Delta2))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta2==Delta(1,1) 
    kdi2=kdib(1,1) 
 elseif Cond==1 && Delta2==Delta(1,2) 
    kdi2=kdib(1,2)  
 elseif Cond==1 && Delta2==Delta(1,3) 
    kdi2=kdib(1,3)
 elseif Cond==1 && Delta2==Delta(1,4) 
    kdi2=kdib(1,4)
 elseif Cond==1 && Delta2==Delta(1,5) 
    kdi2=kdib(1,5)    
 elseif Cond==1 && Delta2==Delta(1,6) 
    kdi2=kdib(1,6)
 elseif Cond==1 && Delta2==Delta(1,7) 
    kdi2=kdib(1,7)    
 elseif Cond==2 && Delta2==Delta(1,1) 
    kdi2=kdil(1,1)
 elseif Cond==2 && Delta2==Delta(1,2) 
    kdi2=kdil(1,2)  
 elseif Cond==2 && Delta2==Delta(1,3) 
    kdi2=kdil(1,3)
 elseif Cond==2 && Delta2==Delta(1,4) 
    kdi2=kdil(1,4)
 elseif Cond==2 && Delta2==Delta(1,5) 
    kdi2=kdil(1,5)    
 elseif Cond==2 && Delta2==Delta(1,6) 
    kdi2=kdil(1,6)
 elseif Cond==2 && Delta2==Delta(1,7) 
    kdi2=kdil(1,7)   
 else 
     kdi2=1
    end

if Turn2>60
    kt2=0.8
else
    kt2=1
end
if Turn2<25
    kt22=0.3
else
    kt22=1
end
if Cond==1 && Delta2<=15
    Kh2=2.01
elseif Cond==1 && Delta2>=20
    Kh2=1.35
elseif Cond==2 && Delta2<=15
    Kh2=6.7
elseif Cond==2 && Delta2>=20
    Kh2=4.5
end
if D3<=3.5*LOA && sign(step2)==sign(step3)
kdt2=0.3
else
kdt2=1
end
p2=2
if p2<length(unique(Turning2))
b1=Turning2(1,p1)
else
b1=Emp
end
LAThj1=LatH2 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b1*pi/180)
Longhj1=LongH2+ Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b1*pi/180)     
if p2+1<=length(unique(Turning2)) && Turn1>4 b2=Turning2(1,p2+1)
else b2=Emp
end
LAThj2=LAThj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*cos(b2*pi/180)
LONGhj2=LONGhj1 + Kh2*kdt2*kt22*kt2*kdi2*do2*sin(b2*pi/180)     
if p2+2<=length(unique(Turning2)) b3=Turning2(1,p2+2)
else b3=Emp
end
LAThj3=LAThj2 + kt2*kdi2*do2*cos(b3*pi/180)
LONGhj3=LONGhj2 + kt2*kdi2*do2*sin(b3*pi/180)     
if p2+3<=length(unique(Turning2)) b4=Turning2(1,p2+3) 
else b4=Emp; 
end
LAThj4=LAThj3 + kt2*kdi2*do2*cos(b4*pi/180);
LONGhj4=LONGhj3 + kt2*kdi2*do2*sin(b4*pi/180)     
if  p2+4<=length(unique(Turning2)) b5=Turning2(1,p2+4) 
else b5=Emp 
end
LAThj5=LAThj4 + kt2*kdi2*do2*cos(b5*pi/180)
LONGhj5=LONGhj4 + kt2*kdi2*do2*sin(b5*pi/180)     
if p2+5<=length(unique(Turning2)) b6=Turning2(1,p2+5) 
else b6=Emp 
end
LAThj6=LAThj5 + kt2*kdi2*do2*cos(b6*pi/180)
LONGhj6=LONGhj5 + kt2*kdi2*do2*sin(b6*pi/180)     
if p2+6<=length(unique(Turning2)) b7=Turning2(1,p2+6) 
else b7=Emp 
end
LAThj7=LAThj6 + kt2*kdi2*do2*cos(b7*pi/180)
LONGhj7=LONGhj6 + kt2*kdi2*do2*sin(b7*pi/180)     
if p2+7<=length(unique(Turning2)) b8=Turning2(1,p2+7) 
else b8=Emp 
end
LAThj8=LAThj7 + kt2*kdi2*do2*cos(b8*pi/180)
LONGhj8=LONGhj7 + kt2*kdi2*do2*sin(b8*pi/180)     
if  p2+8<=length(unique(Turning2)) b9=Turning2(1,p2+8) 
else b9=Emp 
end
LAThj9=LAThj8 + kt2*kdi2*do2*cos(b9*pi/180)
LONGhj9=LONGhj8 + kt2*kdi2*do2*sin(b9*pi/180)     
if p2+9<=length(unique(Turning2)) b10=Turning2(1,p2+9) 
else b10=Emp 
end
LAThj10=LAThj9 + kt2*kdi2*do2*cos(b10*pi/180)
LONGhj10=LONGhj9 + kt2*kdi2*do2*sin(b10*pi/180)     
if p2+10<=length(unique(Turning2)) b11=Turning2(1,p2+10) 
else b11=Emp 
end
LAThj11=LAThj10 + kt2*kdi2*do2*cos(b11*pi/180)
LONGhj11=LONGhj10 + kt2*kdi2*do2*sin(b11*pi/180)     
if p2+11<=length(unique(Turning2)) b12=Turning2(1,p2+11) 
else b12=Emp 
end
LAThj12=LAThj11 + kt2*kdi2*do2*cos(b12*pi/180)
LONGhj12=LONGhj11 + kt2*kdi2*do2*sin(b12*pi/180)     
if p2+12<=length(unique(Turning2)) b13=Turning2(1,p2+12) 
else b13=Emp 
end
LAThj13=LAThj12 + kt2*kdi2*do2*cos(b13*pi/180)
LONGhj13=LONGhj12 + kt2*kdi2*do2*sin(b13*pi/180)     
if p2+13<=length(unique(Turning2)) b14=Turning2(1,p2+13) 
else b14=Emp 
end
LAThj14=LAThj13 + kt2*kdi2*do2*cos(b14*pi/180)
LONGhj14=LONGhj13 + kt2*kdi2*do2*sin(b14*pi/180)     
if p2+14<=length(unique(Turning2)) b15=Turning2(1,p2+14) 
else b15=Emp 
end
LAThj15=LAThj14 + kt2*kdi2*do2*cos(b15*pi/180)
LONGhj15=LONGhj14 + kt2*kdi2*do2*sin(b15*pi/180)     
if p2+15<=length(unique(Turning2)) b16=Turning2(1,p2+15) 
else b16=Emp 
end
LAThj16=LAThj15 + kt2*kdi2*do2*cos(b16*pi/180)
LONGhj16=LONGhj15 + kt2*kdi2*do2*sin(b16*pi/180)     
if p2+16<=length(unique(Turning2)) b17=Turning2(1,p2+16) 
else b17=Emp 
end
LAThj17=LAThj16 + kt2*kdi2*do2*cos(b17*pi/180)
LONGhj17=LONGhj16 + kt2*kdi2*do2*sin(b17*pi/180)     
if p2+17<=length(unique(Turning2))  b18=Turning2(1,p2+17) 
else b18=Emp 
end
LAThj18=LAThj17 + kt2*kdi2*do2*cos(b18*pi/180)
LONGhj18=LONGhj17 + kt2*kdi2*do2*sin(b18*pi/180)     
if p2+18<=length(unique(Turning2)) b19=Turning2(1,p2+18) 
else b19=Emp 
end
LAThj19=LAThj18 + kt2*kdi2*do2*cos(b19*pi/180)
LONGhj19=LONGhj18 + kt2*kdi2*do2*sin(b19*pi/180)     
if p2+19<=length(unique(Turning2)) b20=Turning2(1,p2+19) 
else b20=Emp 
end
LAThj20=LAThj19 + kt2*kdi2*do2*cos(b20*pi/180)
LONGhj20=LONGhj19 + kt2*kdi2*do2*sin(b20*pi/180)     
if p2+20<=length(unique(Turning2)) b21=Turning2(1,p2+20) 
else b21=Emp 
end
LAThj21=LAThj20 + kt2*kdi2*do2*cos(b21*pi/180)
LONGhj21=LONGhj20 + kt2*kdi2*do2*sin(b21*pi/180)     
if p2+21<=length(unique(Turning2)) b22=Turning2(1,p2+21) 
else b22=Emp 
end
LAThj22=LAThj21 + kt2*kdi2*do2*cos(b22*pi/180)
LONGhj22=LONGhj21 + kt2*kdi2*do2*sin(b22*pi/180)     
if p2+22<=length(unique(Turning2)) b23=Turning2(1,p2+22) 
else b23=Emp 
end
LAThj23=LAThj22 + kt2*kdi2*do2*cos(b23*pi/180)
LONGhj23=LONGhj22 + kt2*kdi2*do2*sin(b23*pi/180)     
if p2+23<=length(unique(Turning2)) b24=Turning2(1,p2+23) 
else b24=Emp 
end
LAThj24=LAThj23 + kt2*kdi2*do2*cos(b24*pi/180)
LONGhj24=LONGhj23 + kt2*kdi2*do2*sin(b24*pi/180)     
if p2+24<=length(unique(Turning2)) b25=Turning2(1,p2+24) 
else b25=Emp 
end 
LAThj25=LAThj24 + kt2*kdi2*do2*cos(b25*pi/180)
LONGhj25=LONGhj24 + kt2*kdi2*do2*sin(b25*pi/180)     
if p2+25<=length(unique(Turning2)) b26=Turning2(1,p2+25) 
else b26=Emp 
end 
LAThj26=LAThj25 + kt2*kdi2*do2*cos(b26*pi/180)
LONGhj26=LONGhj25 + kt2*kdi2*do2*sin(b26*pi/180)     
if p2+26<=length(unique(Turning2)) b27=Turning2(1,p2+26) 
else b27=Emp 
end 
LAThj27=LAThj26 + kt2*kdi2*do2*cos(b27*pi/180)
LONGhj27=LONGhj26 + kt2*kdi2*do2*sin(b27*pi/180)     
if p2+27<=length(unique(Turning2)) b28=Turning2(1,p2+27) 
else b28=Emp 
end 
LAThj28=LAThj27 + kt2*kdi2*do2*cos(b28*pi/180)
LONGhj28=LONGhj27 + kt2*kdi2*do2*sin(b28*pi/180)     
if p2+28<=length(unique(Turning2)) b29=Turning2(1,p2+28) 
else b29=Emp 
end 
LAThj29=LAThj28 + kt2*kdi2*do2*cos(b29*pi/180)
LONGhj29=LONGhj28 + kt2*kdi2*do2*sin(b29*pi/180)     
if p2+29<=length(unique(Turning2)) b30=Turning2(1,p2+29) 
else b30=Emp 
end 
LAThj30=LAThj29 + kt2*kdi2*do2*cos(b30*pi/180)
LONGhj30=LONGhj29 + kt2*kdi2*do2*sin(b30*pi/180)     
if p2+30<=length(unique(Turning2)) b31=Turning2(1,p2+30) 
else b31=Emp 
end 
LAThj31=LAThj30 + kt2*kdi2*do2*cos(b31*pi/180)
LONGhj31=LONGhj30 + kt2*kdi2*do2*sin(b31*pi/180)     
if p2+31<=length(unique(Turning2)) b32=Turning2(1,p2+31) 
else b32=Emp 
end 
LAThj32=LAThj31 + kt2*kdi2*do2*cos(b32*pi/180)
LONGhj32=LONGhj31 + kt2*kdi2*do2*sin(b32*pi/180)     
if p2+32<=length(unique(Turning2)) b33=Turning2(1,p2+32)
else b33=Emp
end
LAThj33=LAThj32 + kt2*kdi2*do2*cos(b33*pi/180)
LONGhj33=LONGhj32 + kt2*kdi2*do2*sin(b33*pi/180)     
if p2+33<=length(unique(Turning2)) b34=Turning2(1,p2+33) 
else b34=Emp 
end
LAThj34=LAThj33 + kt2*kdi2*do2*cos(b34*pi/180)
LONGhj34=LONGhj33 + kt2*kdi2*do2*sin(b34*pi/180)     
if p2+34<=length(unique(Turning2)) b35=Turning2(1,p2+34) 
else b35=Emp 
end
LAThj35=LAThj34 + kt2*kdi2*do2*cos(b35*pi/180)
LONGhj35=LONGhj34 + kt2*kdi2*do2*sin(b35*pi/180)     
if p2+35<=length(unique(Turning2)) b36=Turning2(1,p2+35) 
else b36=Emp 
end
LAThj36=LAThj35 + kt2*kdi2*do2*cos(b36*pi/180)
LONGhj36=LONGhj35 + kt2*kdi2*do2*sin(b36*pi/180)     
if p2+36<=length(unique(Turning2)) b37=Turning2(1,p2+36) 
else b37=Emp 
end
LAThj37=LAThj36 + kt2*kdi2*do2*cos(b37*pi/180)
LONGhj37=LONGhj36 + kt2*kdi2*do2*sin(b37*pi/180)     
if p2+37<=length(unique(Turning2)) b38=Turning2(1,p2+37) 
else b38=Emp 
end
LAThj38=LAThj37 + kt2*kdi2*do2*cos(b38*pi/180)
LONGhj38=LONGhj37 + kt2*kdi2*do2*sin(b38*pi/180)     
if p2+38<=length(unique(Turning2)) b39=Turning2(1,p2+38) 
else b39=Emp 
end
LAThj39=LAThj38 + kt2*kdi2*do2*cos(b39*pi/180)
LONGhj39=LONGhj38 + kt2*kdi2*do2*sin(b39*pi/180)     
if p2+39<=length(unique(Turning2)) b40=Turning2(1,p2+39) 
else b40=Emp 
end
LAThj40=LAThj39 + kt2*kdi2*do2*cos(b40*pi/180)
LONGhj40=LONGhj39 + kt2*kdi2*do2*sin(b40*pi/180)     
if p2+40<=length(unique(Turning2)) b41=Turning2(1,p2+40) 
else b41=Emp 
end
LAThj41=LAThj40 + kt2*kdi2*do2*cos(b41*pi/180)
LONGhj41=LONGhj40 + kt2*kdi2*do2*sin(b41*pi/180)     
if p2+41<=length(unique(Turning2)) b42=Turning2(1,p2+41) 
else b42=Emp 
end
LAThj42=LAThj41 + kt2*kdi2*do2*cos(b42*pi/180)
LONGhj42=LONGhj41 + kt2*kdi2*do2*sin(b42*pi/180)     
if p2+42<=length(unique(Turning2)) b43=Turning2(1,p2+42) 
else b43=Emp 
end
LAThj43=LAThj42 + kt2*kdi2*do2*cos(b43*pi/180)
LONGhj43=LONGhj42 + kt2*kdi2*do2*sin(b43*pi/180)     
if p2+43<=length(unique(Turning2)) b44=Turning2(1,p2+43) 
else b44=Emp 
end
LAThj44=LAThj43 + kt2*kdi2*do2*cos(b44*pi/180)
LONGhj44=LONGhj43 + kt2*kdi2*do2*sin(b44*pi/180)     
if p2+44<=length(unique(Turning2)) b45=Turning2(1,p2+44) 
else b45=Emp 
end
LAThj45=LAThj44 + kt2*kdi2*do2*cos(b45*pi/180)
LONGhj45=LONGhj44 + kt2*kdi2*do2*sin(b45*pi/180)     
if p2+45<=length(unique(Turning2)) b46=Turning2(1,p2+45) 
else b46=Emp 
end
LAThj46=LAThj45 + kt2*kdi2*do2*cos(b46*pi/180)
LONGhj46=LONGhj45 + kt2*kdi2*do2*sin(b46*pi/180)     
if p2+46<=length(unique(Turning2)) b47=Turning2(1,p2+46) 
else b47=Emp 
end
LAThj47=LAThj46 + kt2*kdi2*do2*cos(b47*pi/180)
LONGhj47=LONGhj46 + kt2*kdi2*do2*sin(b47*pi/180)     
if p2+47<=length(unique(Turning2)) b48=Turning2(1,p2+47) 
else b48=Emp 
end
LAThj48=LAThj47 + kt2*kdi2*do2*cos(b48*pi/180)
LONGhj48=LONGhj47 + kt2*kdi2*do2*sin(b48*pi/180)     
if p2+48<=length(unique(Turning2)) b49=Turning2(1,p2+48) 
else b49=Emp 
end
LAThj49=LAThj48 + kt2*kdi2*do2*cos(b49*pi/180)
LONGhj49=LONGhj48 + kt2*kdi2*do2*sin(b49*pi/180)     
if p2+49<=length(unique(Turning2)) b50=Turning2(1,p2+49) 
else b50=Emp 
end
LAThj50=LAThj49 + kt2*kdi2*do2*cos(b50*pi/180)
LONGhj50=LONGhj49 + kt2*kdi2*do2*sin(b50*pi/180)     
if p2+50<=length(unique(Turning2)) b51=Turning2(1,p2+50) 
else b51=Emp 
end
LAThj51=LAThj50 + kt2*kdi2*do2*cos(b51*pi/180)
LONGhj51=LONGhj50 + kt2*kdi2*do2*sin(b51*pi/180)     
if p2+51<=length(unique(Turning2)) b52=Turning2(1,p2+51) 
else b52=Emp 
end
LAThj52=LAThj51 + kt2*kdi2*do2*cos(b52*pi/180)
LONGhj52=LONGhj51 + kt2*kdi2*do2*sin(b52*pi/180)     
if p2+52<=length(unique(Turning2)) b53=Turning2(1,p2+52) 
else b53=Emp 
end
LAThj53=LAThj52 + kt2*kdi2*do2*cos(b53*pi/180)
LONGhj53=LONGhj52 + kt2*kdi2*do2*sin(b53*pi/180)     
if p2+53<=length(unique(Turning2)) b54=Turning2(1,p2+53) 
else b54=Emp 
end
LAThj54=LAThj53 + kt2*kdi2*do2*cos(b54*pi/180)
LONGhj54=LONGhj53 + kt2*kdi2*do2*sin(b54*pi/180)     
if p2+54<=length(unique(Turning2)) b55=Turning2(1,p2+54) 
else b55=Emp 
end 
LAThj55=LAThj54 + kt2*kdi2*do2*cos(b55*pi/180)
LONGhj55=LONGhj54 + kt2*kdi2*do2*sin(b55*pi/180)     
if p2+55<=length(unique(Turning2)) b56=Turning2(1,p2+55) 
else b56=Emp 
end 
LAThj56=LAThj55 + kt2*kdi2*do2*cos(b56*pi/180)
LONGhj56=LONGhj55 + kt2*kdi2*do2*sin(b56*pi/180)     
if p2+56<=length(unique(Turning2)) b57=Turning2(1,p2+56) 
else b57=Emp 
end 
LAThj57=LAThj56 + kt2*kdi2*do2*cos(b57*pi/180)
LONGhj57=LONGhj56 + kt2*kdi2*do2*sin(b57*pi/180)     
if p2+57<=length(unique(Turning2)) b58=Turning2(1,p2+57) 
else b58=Emp 
end 
LAThj58=LAThj57 + kt2*kdi2*do2*cos(b58*pi/180)
LONGhj58=LONGhj57 + kt2*kdi2*do2*sin(b58*pi/180)     
if p2+58<=length(unique(Turning2)) b59=Turning2(1,p2+58) 
else b59=Emp 
end 
LAThj59=LAThj58 + kt2*kdi2*do2*cos(b59*pi/180)
LONGhj59=LONGhj58 + kt2*kdi2*do2*sin(b59*pi/180)     
if p2+59<=length(unique(Turning2)) b60=Turning2(1,p2+59) 
else b60=Emp 
end 
LAThj60=LAThj59 + kt2*kdi2*do2*cos(b60*pi/180)
LONGhj60=LONGhj59 + kt2*kdi2*do2*sin(b60*pi/180)

if TA==1 && Turn3<=10
        Delta3=Delta(1,1) 
 elseif TA==1 && Turn3<=30
        Delta3=Delta(1,2)   
 elseif TA==1 && Turn3<=40
        Delta3=Delta(1,3) 
 elseif TA==1 && Turn3<=50
        Delta3=Delta(1,4)  
 elseif TA==1 && Turn3<=55
        Delta3=Delta(1,5)     
 elseif TA==1 && Turn3<=60
        Delta3=Delta(1,6)
 elseif TA==1 && Turn3>60
        Delta3=Delta(1,7)     
 elseif TA==2 && Turn3<=10
        Delta3=Delta(1,1)
 elseif TA==2 && Turn3<=20
        Delta3=Delta(1,2)
 elseif TA==2 && Turn3<=30
        Delta3=Delta(1,3) 
 elseif TA==2 && Turn3<=40
        Delta3=Delta(1,4)  
 elseif TA==2 && Turn3<=45
        Delta3=Delta(1,5)     
 elseif TA==2 && Turn3<=55
        Delta3=Delta(1,6)
 elseif TA==2 && Turn3>55
        Delta3=Delta(1,7) 
 elseif TA==3 && Turn3<=5
        Delta3=Delta(1,1)
 elseif TA==3 && Turn3<=10
        Delta3=Delta(1,2)
 elseif TA==3 && Turn3<=20
        Delta3=Delta(1,3) 
 elseif TA==3 && Turn3<=30
        Delta3=Delta(1,4)  
 elseif TA==3 && Turn3<=40
        Delta3=Delta(1,5)     
 elseif TA==3 && Turn3<=45
        Delta3=Delta(1,6)
 elseif TA==3 && Turn3>45
        Delta3=Delta(1,7) 
 elseif max(length(x1))<5 
        Delta3=0
 end

if Turn3<=90 && Cond==1
do3=((11.75*(F1./sqrt(Delta3))+1.35*dT1-3.9)*gdt1*(LPP)*pi/dpsi) 
elseif Turn3<=90 && Cond==2
do3=((11.75*(F2./sqrt(Delta3))+1.35*dT2-3.9)*gdt2*(LPP)*pi/dpsi) 
elseif Cond==1 
do3=((11.61*(F1/sqrt(Delta3))+1.2*dT1-4.31)*gdu1*(LPP)*pi/dpsi) 
elseif Cond==2 
do3=((11.61*(F2/sqrt(Delta3))+1.2*dT2-4.31)*gdu2*(LPP)*pi/dpsi) 
end

 if Cond==1 && Delta3==Delta(1,1) 
    kdi3=kdib(1,1) 
 elseif Cond==1 && Delta3==Delta(1,2) 
    kdi3=kdib(1,2)  
 elseif Cond==1 && Delta3==Delta(1,3) 
    kdi3=kdib(1,3)
 elseif Cond==1 && Delta3==Delta(1,4) 
    kdi3=kdib(1,4)
 elseif Cond==1 && Delta3==Delta(1,5) 
    kdi3=kdib(1,5)    
 elseif Cond==1 && Delta3==Delta(1,6) 
    kdi3=kdib(1,6)
 elseif Cond==1 && Delta3==Delta(1,7) 
    kdi3=kdib(1,7)    
 elseif Cond==2 && Delta3==Delta(1,1) 
    kdi3=kdil(1,1)
 elseif Cond==2 && Delta3==Delta(1,2) 
    kdi3=kdil(1,2)  
 elseif Cond==2 && Delta3==Delta(1,3) 
    kdi3=kdil(1,3)
 elseif Cond==2 && Delta3==Delta(1,4) 
    kdi3=kdil(1,4)
 elseif Cond==2 && Delta3==Delta(1,5) 
    kdi3=kdil(1,5)    
 elseif Cond==2 && Delta3==Delta(1,6) 
    kdi3=kdil(1,6)
 elseif Cond==2 && Delta3==Delta(1,7) 
    kdi3=kdil(1,7)
 else
    kdi3=1
    end

if Turn3>60
    kt3=0.8
else
    kt3=1
end
if Turn3<25
    kt23=0.3
else
    kt23=1
end
if Cond==1 && Delta3<=15
    Kh3=2.01
elseif Cond==1 && Delta3>=20
    Kh3=1.35
elseif Cond==2 && Delta3<=15
    Kh3=6.7
elseif Cond==2 && Delta3>=20
    Kh3=4.5
end
if D4<=3.5*LOA 
kdt3=0.3
else
kdt3=1
end
p3=2
if p3<length(unique(Turning3))
c1=Turning3(1,p3)
else
c1=Emp
end
LAThk1=LatH3 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c1*pi/180)
LONGhk1=LongH3+ Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c1*pi/180)     
if p3+1<=length(unique(Turning3)) && Turn1>4 c2=Turning3(1,p3+1)
else c2=Emp
end
LAThk2=LAThk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*cos(c2*pi/180)
LONGhk2=LONGhk1 + Kh3*kdt3*kt23*kt3*kdi3*do3*sin(c2*pi/180)     
if p3+2<=length(unique(Turning3)) c3=Turning3(1,p3+2)
else c3=Emp
end
LAThk3=LAThk2 + kt3*kdi3*do3*cos(c3*pi/180)
LONGhk3=LONGhk2 + kt3*kdi3*do3*sin(c3*pi/180)     
if p3+3<=length(unique(Turning3)) c4=Turning3(1,p3+3) 
else c4=Emp; 
end
LAThk4=LAThk3 + kt3*kdi3*do3*cos(c4*pi/180);
LONGhk4=LONGhk3 + kt3*kdi3*do3*sin(c4*pi/180)     
if  p3+4<=length(unique(Turning3)) c5=Turning3(1,p3+4) 
else c5=Emp 
end
LAThk5=LAThk4 + kt3*kdi3*do3*cos(c5*pi/180)
LONGhk5=LONGhk4 + kt3*kdi3*do3*sin(c5*pi/180)     
if p3+5<=length(unique(Turning3)) c6=Turning3(1,p3+5) 
else c6=Emp 
end
LAThk6=LAThk5 + kt3*kdi3*do3*cos(c6*pi/180)
LONGhk6=LONGhk5 + kt3*kdi3*do3*sin(c6*pi/180)     
if p3+6<=length(unique(Turning3)) c7=Turning3(1,p3+6) 
else c7=Emp 
end
LAThk7=LAThk6 + kt3*kdi3*do3*cos(c7*pi/180)
LONGhk7=LONGhk6 + kt3*kdi3*do3*sin(c7*pi/180)     
if p3+7<=length(unique(Turning3)) c8=Turning3(1,p3+7) 
else c8=Emp 
end
LAThk8=LAThk7 + kt3*kdi3*do3*cos(c8*pi/180)
LONGhk8=LONGhk7 + kt3*kdi3*do3*sin(c8*pi/180)     
if  p3+8<=length(unique(Turning3)) c9=Turning3(1,p3+8) 
else c9=Emp 
end
LAThk9=LAThk8 + kt3*kdi3*do3*cos(c9*pi/180)
LONGhk9=LONGhk8 + kt3*kdi3*do3*sin(c9*pi/180)     
if p3+9<=length(unique(Turning3)) c10=Turning3(1,p3+9) 
else c10=Emp 
end
LAThk10=LAThk9 + kt3*kdi3*do3*cos(c10*pi/180)
LONGhk10=LONGhk9 + kt3*kdi3*do3*sin(c10*pi/180)     
if p3+10<=length(unique(Turning3)) c11=Turning3(1,p3+10) 
else c11=Emp 
end
LAThk11=LAThk10 + kt3*kdi3*do3*cos(c11*pi/180)
LONGhk11=LONGhk10 + kt3*kdi3*do3*sin(c11*pi/180)     
if p3+11<=length(unique(Turning3)) c12=Turning3(1,p3+11) 
else c12=Emp 
end
LAThk12=LAThk11 + kt3*kdi3*do3*cos(c12*pi/180)
LONGhk12=LONGhk11 + kt3*kdi3*do3*sin(c12*pi/180)     
if p3+12<=length(unique(Turning3)) c13=Turning3(1,p3+12) 
else c13=Emp 
end
LAThk13=LAThk12 + kt3*kdi3*do3*cos(c13*pi/180)
LONGhk13=LONGhk12 + kt3*kdi3*do3*sin(c13*pi/180)     
if p3+13<=length(unique(Turning3)) c14=Turning3(1,p3+13) 
else c14=Emp 
end
LAThk14=LAThk13 + kt3*kdi3*do3*cos(c14*pi/180)
LONGhk14=LONGhk13 + kt3*kdi3*do3*sin(c14*pi/180)     
if p3+14<=length(unique(Turning3)) c15=Turning3(1,p3+14) 
else c15=Emp 
end
LAThk15=LAThk14 + kt3*kdi3*do3*cos(c15*pi/180)
LONGhk15=LONGhk14 + kt3*kdi3*do3*sin(c15*pi/180)     
if p3+15<=length(unique(Turning3)) c16=Turning3(1,p3+15) 
else c16=Emp 
end
LAThk16=LAThk15 + kt3*kdi3*do3*cos(c16*pi/180)
LONGhk16=LONGhk15 + kt3*kdi3*do3*sin(c16*pi/180)     
if p3+16<=length(unique(Turning3)) c17=Turning3(1,p3+16) 
else c17=Emp 
end
LAThk17=LAThk16 + kt3*kdi3*do3*cos(c17*pi/180)
LONGhk17=LONGhk16 + kt3*kdi3*do3*sin(c17*pi/180)     
if p3+17<=length(unique(Turning3))  c18=Turning3(1,p3+17) 
else c18=Emp 
end
LAThk18=LAThk17 + kt3*kdi3*do3*cos(c18*pi/180)
LONGhk18=LONGhk17 + kt3*kdi3*do3*sin(c18*pi/180)     
if p3+18<=length(unique(Turning3)) c19=Turning3(1,p3+18) 
else c19=Emp 
end
LAThk19=LAThk18 + kt3*kdi3*do3*cos(c19*pi/180)
LONGhk19=LONGhk18 + kt3*kdi3*do3*sin(c19*pi/180)     
if p3+19<=length(unique(Turning3)) c20=Turning3(1,p3+19) 
else c20=Emp 
end
LAThk20=LAThk19 + kt3*kdi3*do3*cos(c20*pi/180)
LONGhk20=LONGhk19 + kt3*kdi3*do3*sin(c20*pi/180)     
if p3+20<=length(unique(Turning3)) c21=Turning3(1,p3+20) 
else c21=Emp 
end
LAThk21=LAThk20 + kt3*kdi3*do3*cos(c21*pi/180)
LONGhk21=LONGhk20 + kt3*kdi3*do3*sin(c21*pi/180)     
if p3+21<=length(unique(Turning3)) c22=Turning3(1,p3+21) 
else c22=Emp 
end
LAThk22=LAThk21 + kt3*kdi3*do3*cos(c22*pi/180)
LONGhk22=LONGhk21 + kt3*kdi3*do3*sin(c22*pi/180)     
if p3+22<=length(unique(Turning3)) c23=Turning3(1,p3+22) 
else c23=Emp 
end
LAThk23=LAThk22 + kt3*kdi3*do3*cos(c23*pi/180)
LONGhk23=LONGhk22 + kt3*kdi3*do3*sin(c23*pi/180)     
if p3+23<=length(unique(Turning3)) c24=Turning3(1,p3+23) 
else c24=Emp 
end
LAThk24=LAThk23 + kt3*kdi3*do3*cos(c24*pi/180)
LONGhk24=LONGhk23 + kt3*kdi3*do3*sin(c24*pi/180)     
if p3+24<=length(unique(Turning3)) c25=Turning3(1,p3+24) 
else c25=Emp 
end 
LAThk25=LAThk24 + kt3*kdi3*do3*cos(c25*pi/180)
LONGhk25=LONGhk24 + kt3*kdi3*do3*sin(c25*pi/180)     
if p3+25<=length(unique(Turning3)) c26=Turning3(1,p3+25) 
else c26=Emp 
end 
LAThk26=LAThk25 + kt3*kdi3*do3*cos(c26*pi/180)
LONGhk26=LONGhk25 + kt3*kdi3*do3*sin(c26*pi/180)     
if p3+26<=length(unique(Turning3)) c27=Turning3(1,p3+26) 
else c27=Emp 
end 
LAThk27=LAThk26 + kt3*kdi3*do3*cos(c27*pi/180)
LONGhk27=LONGhk26 + kt3*kdi3*do3*sin(c27*pi/180)     
if p3+27<=length(unique(Turning3)) c28=Turning3(1,p3+27) 
else c28=Emp 
end 
LAThk28=LAThk27 + kt3*kdi3*do3*cos(c28*pi/180)
LONGhk28=LONGhk27 + kt3*kdi3*do3*sin(c28*pi/180)     
if p3+28<=length(unique(Turning3)) c29=Turning3(1,p3+28) 
else c29=Emp 
end 
LAThk29=LAThk28 + kt3*kdi3*do3*cos(c29*pi/180)
LONGhk29=LONGhk28 + kt3*kdi3*do3*sin(c29*pi/180)     
if p3+29<=length(unique(Turning3)) c30=Turning3(1,p3+29) 
else c30=Emp 
end 
LAThk30=LAThk29 + kt3*kdi3*do3*cos(c30*pi/180)
LONGhk30=LONGhk29 + kt3*kdi3*do3*sin(c30*pi/180)     
if p3+30<=length(unique(Turning3)) c31=Turning3(1,p3+30) 
else c31=Emp 
end 
LAThk31=LAThk30 + kt3*kdi3*do3*cos(c31*pi/180)
LONGhk31=LONGhk30 + kt3*kdi3*do3*sin(c31*pi/180)     
if p3+31<=length(unique(Turning3)) c32=Turning3(1,p3+31) 
else c32=Emp 
end 
LAThk32=LAThk31 + kt3*kdi3*do3*cos(c32*pi/180)
LONGhk32=LONGhk31 + kt3*kdi3*do3*sin(c32*pi/180)     
if p3+32<=length(unique(Turning3)) c33=Turning3(1,p3+32)
else c33=Emp
end
LAThk33=LAThk32 + kt3*kdi3*do3*cos(c33*pi/180)
LONGhk33=LONGhk32 + kt3*kdi3*do3*sin(c33*pi/180)     
if p3+33<=length(unique(Turning3)) c34=Turning3(1,p3+33) 
else c34=Emp 
end
LAThk34=LAThk33 + kt3*kdi3*do3*cos(c34*pi/180)
LONGhk34=LONGhk33 + kt3*kdi3*do3*sin(c34*pi/180)     
if p3+34<=length(unique(Turning3)) c35=Turning3(1,p3+34) 
else c35=Emp 
end
LAThk35=LAThk34 + kt3*kdi3*do3*cos(c35*pi/180)
LONGhk35=LONGhk34 + kt3*kdi3*do3*sin(c35*pi/180)     
if p3+35<=length(unique(Turning3)) c36=Turning3(1,p3+35) 
else c36=Emp 
end
LAThk36=LAThk35 + kt3*kdi3*do3*cos(c36*pi/180)
LONGhk36=LONGhk35 + kt3*kdi3*do3*sin(c36*pi/180)     
if p3+36<=length(unique(Turning3)) c37=Turning3(1,p3+36) 
else c37=Emp 
end
LAThk37=LAThk36 + kt3*kdi3*do3*cos(c37*pi/180)
LONGhk37=LONGhk36 + kt3*kdi3*do3*sin(c37*pi/180)     
if p3+37<=length(unique(Turning3)) c38=Turning3(1,p3+37) 
else c38=Emp 
end
LAThk38=LAThk37 + kt3*kdi3*do3*cos(c38*pi/180)
LONGhk38=LONGhk37 + kt3*kdi3*do3*sin(c38*pi/180)     
if p3+38<=length(unique(Turning3)) c39=Turning3(1,p3+38) 
else c39=Emp 
end
LAThk39=LAThk38 + kt3*kdi3*do3*cos(c39*pi/180)
LONGhk39=LONGhk38 + kt3*kdi3*do3*sin(c39*pi/180)     
if p3+39<=length(unique(Turning3)) c40=Turning3(1,p3+39) 
else c40=Emp 
end
LAThk40=LAThk39 + kt3*kdi3*do3*cos(c40*pi/180)
LONGhk40=LONGhk39 + kt3*kdi3*do3*sin(c40*pi/180)     
if p3+40<=length(unique(Turning3)) c41=Turning3(1,p3+40) 
else c41=Emp 
end
LAThk41=LAThk40 + kt3*kdi3*do3*cos(c41*pi/180)
LONGhk41=LONGhk40 + kt3*kdi3*do3*sin(c41*pi/180)     
if p3+41<=length(unique(Turning3)) c42=Turning3(1,p3+41) 
else c42=Emp 
end
LAThk42=LAThk41 + kt3*kdi3*do3*cos(c42*pi/180)
LONGhk42=LONGhk41 + kt3*kdi3*do3*sin(c42*pi/180)     
if p3+42<=length(unique(Turning3)) c43=Turning3(1,p3+42) 
else c43=Emp 
end
LAThk43=LAThk42 + kt3*kdi3*do3*cos(c43*pi/180)
LONGhk43=LONGhk42 + kt3*kdi3*do3*sin(c43*pi/180)     
if p3+43<=length(unique(Turning3)) c44=Turning3(1,p3+43) 
else c44=Emp 
end
LAThk44=LAThk43 + kt3*kdi3*do3*cos(c44*pi/180)
LONGhk44=LONGhk43 + kt3*kdi3*do3*sin(c44*pi/180)     
if p3+44<=length(unique(Turning3)) c45=Turning3(1,p3+44) 
else c45=Emp 
end
LAThk45=LAThk44 + kt3*kdi3*do3*cos(c45*pi/180)
LONGhk45=LONGhk44 + kt3*kdi3*do3*sin(c45*pi/180)     
if p3+45<=length(unique(Turning3)) c46=Turning3(1,p3+45) 
else c46=Emp 
end
LAThk46=LAThk45 + kt3*kdi3*do3*cos(c46*pi/180)
LONGhk46=LONGhk45 + kt3*kdi3*do3*sin(c46*pi/180)     
if p3+46<=length(unique(Turning3)) c47=Turning3(1,p3+46) 
else c47=Emp 
end
LAThk47=LAThk46 + kt3*kdi3*do3*cos(c47*pi/180)
LONGhk47=LONGhk46 + kt3*kdi3*do3*sin(c47*pi/180)     
if p3+47<=length(unique(Turning3)) c48=Turning3(1,p3+47) 
else c48=Emp 
end
LAThk48=LAThk47 + kt3*kdi3*do3*cos(c48*pi/180)
LONGhk48=LONGhk47 + kt3*kdi3*do3*sin(c48*pi/180)     
if p3+48<=length(unique(Turning3)) c49=Turning3(1,p3+48) 
else c49=Emp 
end
LAThk49=LAThk48 + kt3*kdi3*do3*cos(c49*pi/180)
LONGhk49=LONGhk48 + kt3*kdi3*do3*sin(c49*pi/180)     
if p3+49<=length(unique(Turning3)) c50=Turning3(1,p3+49) 
else c50=Emp 
end
LAThk50=LAThk49 + kt3*kdi3*do3*cos(c50*pi/180)
LONGhk50=LONGhk49 + kt3*kdi3*do3*sin(c50*pi/180)     
if p3+50<=length(unique(Turning3)) c51=Turning3(1,p3+50) 
else c51=Emp 
end
LAThk51=LAThk50 + kt3*kdi3*do3*cos(c51*pi/180)
LONGhk51=LONGhk50 + kt3*kdi3*do3*sin(c51*pi/180)     
if p3+51<=length(unique(Turning3)) c52=Turning3(1,p3+51) 
else c52=Emp 
end
LAThk52=LAThk51 + kt3*kdi3*do3*cos(c52*pi/180)
LONGhk52=LONGhk51 + kt3*kdi3*do3*sin(c52*pi/180)     
if p3+52<=length(unique(Turning3)) c53=Turning3(1,p3+52) 
else c53=Emp 
end
LAThk53=LAThk52 + kt3*kdi3*do3*cos(c53*pi/180)
LONGhk53=LONGhk52 + kt3*kdi3*do3*sin(c53*pi/180)     
if p3+53<=length(unique(Turning3)) c54=Turning3(1,p3+53) 
else c54=Emp 
end
LAThk54=LAThk53 + kt3*kdi3*do3*cos(c54*pi/180)
LONGhk54=LONGhk53 + kt3*kdi3*do3*sin(c54*pi/180)     
if p3+54<=length(unique(Turning3)) c55=Turning3(1,p3+54) 
else c55=Emp 
end 
LAThk55=LAThk54 + kt3*kdi3*do3*cos(c55*pi/180)
LONGhk55=LONGhk54 + kt3*kdi3*do3*sin(c55*pi/180)     
if p3+55<=length(unique(Turning3)) c56=Turning3(1,p3+55) 
else c56=Emp 
end 
LAThk56=LAThk55 + kt3*kdi3*do3*cos(c56*pi/180)
LONGhk56=LONGhk55 + kt3*kdi3*do3*sin(c56*pi/180)     
if p3+56<=length(unique(Turning3)) c57=Turning3(1,p3+56) 
else c57=Emp 
end 
LAThk57=LAThk56 + kt3*kdi3*do3*cos(c57*pi/180)
LONGhk57=LONGhk56 + kt3*kdi3*do3*sin(c57*pi/180)     
if p3+57<=length(unique(Turning3)) c58=Turning3(1,p3+57) 
else c58=Emp 
end 
LAThk58=LAThk57 + kt3*kdi3*do3*cos(c58*pi/180)
LONGhk58=LONGhk57 + kt3*kdi3*do3*sin(c58*pi/180)     
if p3+58<=length(unique(Turning3)) c59=Turning3(1,p3+58) 
else c59=Emp 
end 
LAThk59=LAThk58 + kt3*kdi3*do3*cos(c59*pi/180)
LONGhk59=LONGhk58 + kt3*kdi3*do3*sin(c59*pi/180)     
if p3+59<=length(unique(Turning3)) c60=Turning3(1,p3+59) 
else c60=Emp 
end 
LAThk60=LAThk59 + kt3*kdi3*do3*cos(c60*pi/180)
LONGhk60=LONGhk59 + kt3*kdi3*do3*sin(c60*pi/180)

TM1Lat=[LatH1 LAThi1 LAThi2 LAThi3 LAThi4 LAThi5 LAThi6 LAThi7 LAThi8 LAThi9 LAThi10 LAThi11 LAThi12 LAThi13 LAThi14 LAThi15 LAThi16 LAThi17 LAThi18 LAThi19 LAThi20 LAThi21 LAThi22 LAThi23 LAThi24 LAThi25 LAThi26 LAThi27 LAThi28 LAThi29 LAThi30 LAThi31 LAThi32 LAThi33 LAThi34 LAThi35 LAThi36 LAThi37 LAThi38 LAThi39 LAThi40 LAThi41 LAThi42 LAThi43 LAThi44 LAThi45 LAThi46 LAThi47 LAThi48 LAThi49 LAThi50 LAThi51 LAThi52 LAThi53 LAThi54 LAThi55 LAThi56 LAThi57 LAThi58 LAThi59 LAThi60]
TM1Long=[LongH1 LONGhi1 LONGhi2 LONGhi3 LONGhi4 LONGhi5 LONGhi6 LONGhi7 LONGhi8 LONGhi9 LONGhi10 LONGhi11 LONGhi12 LONGhi13 LONGhi14 LONGhi15 LONGhi16 LONGhi17 LONGhi18 LONGhi19 LONGhi20 LONGhi21 LONGhi22 LONGhi23 LONGhi24 LONGhi25 LONGhi26 LONGhi27 LONGhi28 LONGhi29 LONGhi30 LONGhi31 LONGhi32 LONGhi33 LONGhi34 LONGhi35 LONGhi36 LONGhi37 LONGhi38 LONGhi39 LONGhi40 LONGhi41 LONGhi42 LONGhi43 LONGhi44 LONGhi45 LONGhi46 LONGhi47 LONGhi48 LONGhi49 LONGhi50 LONGhi51 LONGhi52 LONGhi53 LONGhi54 LONGhi55 LONGhi56 LONGhi57 LONGhi58 LONGhi59 LONGhi60]
TM2Lat=[LatH2 LAThj1 LAThj2 LAThj3 LAThj4 LAThj5 LAThj6 LAThj7 LAThj8 LAThj9 LAThj10 LAThj11 LAThj12 LAThj13 LAThj14 LAThj15 LAThj16 LAThj17 LAThj18 LAThj19 LAThj20 LAThj21 LAThj22 LAThj23 LAThj24 LAThj25 LAThj26 LAThj27 LAThj28 LAThj29 LAThj30 LAThj31 LAThj32 LAThj33 LAThj34 LAThj35 LAThj36 LAThj37 LAThj38 LAThj39 LAThj40 LAThj41 LAThj42 LAThj43 LAThj44 LAThj45 LAThj46 LAThj47 LAThj48 LAThj49 LAThj50 LAThj51 LAThj52 LAThj53 LAThj54 LAThj55 LAThj56 LAThj57 LAThj58 LAThj59 LAThj60]
TM2Long=[LongH2 LONGhj1 LONGhj2 LONGhj3 LONGhj4 LONGhj5 LONGhj6 LONGhj7 LONGhj8 LONGhj9 LONGhj10 LONGhj11 LONGhj12 LONGhj13 LONGhj14 LONGhj15 LONGhj16 LONGhj17 LONGhj18 LONGhj19 LONGhj20 LONGhj21 LONGhj22 LONGhj23 LONGhj24 LONGhj25 LONGhj26 LONGhj27 LONGhj28 LONGhj29 LONGhj30 LONGhj31 LONGhj32 LONGhj33 LONGhj34 LONGhj35 LONGhj36 LONGhj37 LONGhj38 LONGhj39 LONGhj40 LONGhj41 LONGhj42 LONGhj43 LONGhj44 LONGhj45 LONGhj46 LONGhj47 LONGhj48 LONGhj49 LONGhj50 LONGhj51 LONGhj52 LONGhj53 LONGhj54 LONGhj55 LONGhj56 LONGhj57 LONGhj58 LONGhj59 LONGhj60]
TM3Lat=[LatH3 LAThk1 LAThk2 LAThk3 LAThk4 LAThk5 LAThk6 LAThk7 LAThk8 LAThk9 LAThk10 LAThk11 LAThk12 LAThk13 LAThk14 LAThk15 LAThk16 LAThk17 LAThk18 LAThk19 LAThk20 LAThk21 LAThk22 LAThk23 LAThk24 LAThk25 LAThk26 LAThk27 LAThk28 LAThk29 LAThk30 LAThk31 LAThk32 LAThk33 LAThk34 LAThk35 LAThk36 LAThk37 LAThk38 LAThk39 LAThk40 LAThk41 LAThk42 LAThk43 LAThk44 LAThk45 LAThk46 LAThk47 LAThk48 LAThk49 LAThk50 LAThk51 LAThk52 LAThk53 LAThk54 LAThk55 LAThk56 LAThk57 LAThk58 LAThk59 LAThk60] 
TM3Long=[LongH3 LONGhk1 LONGhk2 LONGhk3 LONGhk4 LONGhk5 LONGhk6 LONGhk7 LONGhk8 LONGhk9 LONGhk10 LONGhk11 LONGhk12 LONGhk13 LONGhk14 LONGhk15 LONGhk16 LONGhk17 LONGhk18 LONGhk19 LONGhk20 LONGhk21 LONGhk22 LONGhk23 LONGhk24 LONGhk25 LONGhk26 LONGhk27 LONGhk28 LONGhk29 LONGhk30 LONGhk31 LONGhk32 LONGhk33 LONGhk34 LONGhk35 LONGhk36 LONGhk37 LONGhk38 LONGhk39 LONGhk40 LONGhk41  LONGhk42 LONGhk43 LONGhk44 LONGhk45 LONGhk46 LONGhk47 LONGhk48 LONGhk49 LONGhk50 LONGhk51 LONGhk52 LONGhk53 LONGhk54 LONGhk55 LONGhk56 LONGhk57 LONGhk58 LONGhk59 LONGhk60]

%Lokalne planowanie w stopniach
if abs(PM)==abs(PM0)
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5]     
elseif abs(S)==abs(S2a2)
y64=[LatM1 LatH1]
x64=[LongM1 LongH1] 
elseif abs(S)==abs(S2a3)  
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2]
elseif abs(S)==abs(S2a3+S0) 
y64=[LatM1 LatH1]
x64=[LongM1 LongH1]
elseif abs(S)==abs(S2a4)  
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3] 
elseif abs(S)==abs(S2a4+S0) 
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2] 
elseif abs(S)==abs(S2a5) 
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatH3 TM3Lat(1:length(unique(Turning3))-1) LatK3 LatM5]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongH3 TM3Long(1:length(unique(Turning3))-1) LongK3 LongM5] 
elseif abs(S)==abs(S2a5+S0)
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
else
y64=[LatM1 LatH1 TM1Lat(1:length(unique(Turning1))-1) LatK1  LatH2 TM2Lat(1:length(unique(Turning2))-1) LatK2 LatM5]
x64=[LongM1 LongH1 TM1Long(1:length(unique(Turning1))-1) LongK1 LongH2 TM2Long(1:length(unique(Turning2))-1) LongK2 LongM5] 
end



ida=figure;
plot(x14,y14)
hold on
plot(x11,y11)
hold on
plot(x24,y24)
hold on
plot(x21,y21)
hold on
plot(x34,y34)
hold on
plot(x31,y31)
hold on
plot(x44,y44)
hold on
plot(x41,y41)
hold on
plot(x54,y54)
hold on
plot(x51,y51)
hold on
plot(x64,y64)
hold on
plot(x61,y61)
title('Desired route in meters')
xlabel('longitude [m]')
ylabel('latitude [m]')
hold on

idb=figure;

plot(x11,y11)
hold on

plot(x21,y21)
hold on

plot(x31,y31)
hold on

plot(x41,y41)
hold on

plot(x51,y51)
hold on

plot(x61,y61)
title('Desired route in meters')
xlabel('longitude [m]')
ylabel('latitude [m]')
hold on
end



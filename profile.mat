%fill profile vals as tabled (see !!)
clear
close all
x=13:0.1:24;
y=1:301;
[y,x]=meshgrid(y,x);

%% create ideal profile
z=1-0.6*y/1000;
z_up=z+0.3;
CO(:,:,1) = zeros(size(x,1),301); % red
CO(:,:,2) = ones(size(x,1),301); % green
CO(:,:,3) = zeros(size(x,1),301); % blue
s = surf(x,y,z_up,CO,'FaceAlpha',0.5);
s.EdgeColor = 'none';
hold on
z_low=z-0.3;
s = surf(x,y,z_low,CO,'FaceAlpha',0.5);
s.EdgeColor = 'none';

%% !!profile_vals must be entered
profile_vals=[
    1.1 0.9 0.8 1.7 1.0 0.7 0.5;
    1.1 1.3 1.4 1.7 1.0 1.1 0.9;
    1.0 0.8 0.8 0.7 1.0 0.7 0.9;
    0.9 0.9 0.8 0.7 1.0 0.7 0.5;
    1.0 0.9 0.8 1.1 1.0 0.7 0.5;
    0.8 0.9 0.8 1.4 1.0 0.4 0.5;
    0.7 0.9 0.8 1.3 1.0 0.4 0.5;
    0.6 0.9 0.8 1.2 1.0 0.7 0.5;
    0.5 0.9 0.8 1.3 1.0 0.7 0.5;
    0.7 0.5 0.4 0.4 0.6 0.7 0.3;
    1.0 0.9 0.8 1.5 1.0 0.7 0.3;
    1.1 0.9 0.8 1.6 1.0 0.7 0.4
    ];
%% meshgrid
[y_profile_vals,x_profile_vals]=meshgrid(1:50:301,13:24);

p_vals_int=interp2(y_profile_vals,x_profile_vals,profile_vals,y,x);

for i=1:size(p_vals_int,1)
    for j=1:size(p_vals_int,2)
        if p_vals_int(i,j)>z_up(i,j)
            CO(i,j,1) = 1; % red
            CO(i,j,2) = 1; % green
            CO(i,j,3) = 0; % blue
        end
        if p_vals_int(i,j)<z_low(i,j)
            CO(i,j,1) = 1; % red
            CO(i,j,2) = 0; % green
            CO(i,j,3) = 0; % blue
        end
    end
end
hold on;
s = surf(x,y,p_vals_int,CO);
s.LineStyle=':';

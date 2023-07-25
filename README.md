# hex-code-identifier
A simple MATLAB code to get the Hex Codes of any color from a jpg image 
I am providing the code, just copy and run it in MATLAB.
code:
% Read the image into an array
imageFilename = input('Enter file destination:');  % Enter the path of the image file
RGB = imread(imageFilename);

% Display the image
imshow(RGB);

% Enable pixel information display
impixelinfo;

% Wait for user to click on a pixel
disp('Click on a pixel in the image to get its hex code.');
waitforbuttonpress;

% Get the position of the clicked pixel
[x, y] = ginput(1);
x = round(x);
y = round(y);

% Get the RGB values of the clicked pixel
pixelRGB = RGB(y, x, :);

% Convert the RGB values to hex code
hexCode = sprintf('#%02X%02X%02X', pixelRGB(1), pixelRGB(2), pixelRGB(3));

% Display the hex code in the command window
fprintf('Hex Code: %s\n', hexCode);

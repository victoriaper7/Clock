# Clock
Bright bold Clock
let num = [];
let wid;
let cx,cy;

function setup() {
	createCanvas(windowWidth, windowHeight);
	rectMode(CENTER);
	num[0] = [1, 1, 1, 1, 1, 1, 0];
	num[1] = [0, 1, 1, 0, 0, 0, 0];
	num[2] = [1, 1, 0, 1, 1, 0, 1];
	num[3] = [1, 1, 1, 1, 0, 0, 1];
	num[4] = [0, 1, 1, 0, 0, 1, 1];
	num[5] = [1, 0, 1, 1, 0, 1, 1];
	num[6] = [1, 0, 1, 1, 1, 1, 1];
	num[7] = [1, 1, 1, 0, 0, 0, 0];
	num[8] = [1, 1, 1, 1, 1, 1, 1];
	num[9] = [1, 1, 1, 1, 0, 1, 1];
	cx = width/2
	cy = height/2
	wid = width;
	if(width>height)wid = height;
}

let c = ('magenta');
fill(c);
noStroke();
rect(20, 20, 60, 60);

function draw() {
	let hou = hour();
	let min = minute();
	background('magenta');
	fill(0);
	noStroke();
	displayNum(cx-wid*0.7, cy, wid*0.2, wid*0.6, int(hou/10));
	displayNum(cx-wid*0.44, cy, wid*0.2, wid*0.6, int(hou%10));
	displayNum(cx+wid*0.44, cy, wid*0.2, wid*0.6, int(min/10));
	displayNum(cx+wid*0.7, cy, wid*0.2, wid*0.6, int(min%10));
	if(second() % 2 == 0){
		triangle(cx, cy-wid*0.1, wid*0.06);
		triangle(cx, cy+wid*0.1, wid*0.06);
	}
}

function displayNum(x, y, w, h, n){
	let nn = num[n][0];
	let sw = w*0.23;
	let off = w*0.404;
	if(num[n][0])rect(x, y - h/2, w-off, sw);
	if(num[n][1])rect(x+w/2, y - h/4, sw, (h/2)-off);
	if(num[n][2])rect(x+w/2, y + h/4, sw, (h/2)-off);
	if(num[n][3])rect(x, y + h/2, w-off, sw);
	if(num[n][4])rect(x-w/2, y + h/4, sw, (h/2)-off);
	if(num[n][5])rect(x-w/2, y - h/4, sw, (h/2)-off);
	if(num[n][6])rect(x, y, w-off, sw);
	
}


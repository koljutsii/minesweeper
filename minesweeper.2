#!/usr/bin/python
# -*- coding: utf-8 -*-

try:
	import tkinter
except:
	import Tkinter as tkinter
import random

timer = True		#show time count
back_door = True	#hint if press Alt+left_mouse_button
hint = True			#show 'new game' hint (arrow) 

class Cell:
	def __init__(self, canvas, coords):
		x, y, xx, yy = coords
		self.closed = [canvas.create_rectangle(coords[:4], state=vis, fill='grey80', outline='grey80'),	#picture.cover
						canvas.create_line(x,y,xx-1,y, state=vis, fill='white'),
						canvas.create_line(x,y+1,xx-2,y+1, state=vis, fill='white'),
						canvas.create_line(x+2,yy-2,xx,yy-2, state=vis, fill='grey60'),
						canvas.create_line(x+1,yy-1,xx,yy-1, state=vis, fill='grey60'),
						canvas.create_line(x,y,x,yy-1, state=vis, fill='white'),
						canvas.create_line(x+1,y,x+1,yy-2, state=vis, fill='white'),
						canvas.create_line(xx-2,y+2,xx-2,yy, state=vis, fill='grey60'),
						canvas.create_line(xx-1,y+1,xx-1,yy, state=vis, fill='grey60')]
		self.opened = [canvas.create_rectangle(coords[:4], state=hid, fill='grey80', outline='grey50'), #open
						canvas.create_text(x+10,y+10, state=hid, text='', fill='', font='bold', anchor='center')]
		self.flag =   [canvas.create_line(x+8,y+4,x+8,y+16, state=hid, width=2), #flag
						canvas.create_polygon(x+9,y+4,x+9,y+10,x+15,y+7, state=hid, fill='red', outline='red'),
						canvas.create_line(x+5,y+16,x+11,y+16, state=hid, width=2)]
		self.quest =   canvas.create_text(x+10,y+10, state=hid, text='?', font='bold') #question
		self.mine =   [canvas.create_oval(x+4,y+4,xx-4,yy-4, state=hid, fill='grey15'), #mine
						canvas.create_line(x+2,y+10,xx-2,y+10, state=hid, fill='black'),
						canvas.create_line(x+10,y+2,x+10,yy-2, state=hid, fill='black'),
						canvas.create_line(x+5,y+5,xx-4,yy-4, state=hid, fill='black'),
						canvas.create_line(xx-5,y+5,x+4,yy-4, state=hid, fill='black'),
						canvas.create_rectangle(x+7,y+7,x+11,y+11, state=hid, fill='white')]

class Smile:
	def __init__(self, place, coords):
		self.place = place
		x, y, xx, yy = coords
		self.smile_button = [place.create_rectangle(coords, fill='grey80', outline='grey80'), #button
							place.create_line(x,y,xx-1,y, fill='white'),
							place.create_line(x,y+1,xx-2,y+1, fill='white'),
							place.create_line(x+2,yy-2,xx,yy-2, fill='grey60'),
							place.create_line(x+1,yy-1,xx,yy-1, fill='grey60'),
							place.create_line(x,y,x,yy-1, fill='white'),
							place.create_line(x+1,y,x+1,yy-2, fill='white'),
							place.create_line(xx-2,y+2,xx-2,yy, fill='grey60'),
							place.create_line(xx-1,y+1,xx-1,yy, fill='grey60')]
		self.face = [place.create_oval(x+6,y+6,x+34,y+34,fill="yellow"), #face
					place.create_oval(x+14,y+16,x+17,y+19, fill='black'),
					place.create_oval(x+23,y+16,x+26,y+19, fill='black')]
		self.norm = place.create_line(x+13,y+24,x+28,y+24, state=vis) #mouth
		self.good = place.create_polygon(x+13,y+24,x+20,y+29,x+28,y+24, state=hid)
		self.bad = place.create_polygon(x+13,y+29,x+20,y+24,x+28,y+29, state=hid)
		
	def make(self, iter):
		if iter == 'bad':
			self.place.itemconfig(self.norm, state=hid)
			self.place.itemconfig(self.bad, state=vis) #show melancholy
		elif iter == 'good':
			self.place.itemconfig(self.norm, state=hid)
			self.place.itemconfig(self.good, state=vis)	#joy

class Count:
	def __init__(self, place=False, coords=(0,0,0,0), dis=False, st=0, nul=False, border=1000):
		self.place = place
		self.dis = dis
		self.count = st
		self.nul = nul
		self.border = border
		if dis:
			self.back = place.create_rectangle(coords, state=vis, fill='grey30', outline='grey80', width=2)
			self.num = place.create_text(coords[2],coords[3], text='{}'.format(self.count), anchor='se', fill='red3', font='Symbol 26 bold')
			
	def make(self, iter):
		if iter == '+':
			self.count = self.count + 1
		elif iter == '-':
			self.count = self.count - 1
		if self.nul and self.count == self.border:
			self.count = 0
		if self.dis:
			self.place.itemconfig(self.num, text='{}'.format(self.count))

def start(win):
	canvas = tkinter.Canvas(win, width=30*k+s*2, height=16*k+s*2, highlightthickness=0)
	canvas.pack()
	
	canvas.create_rectangle(s,s,602,322, tag='red', fill='red', outline='white', width=2)
	canvas.create_rectangle(s,s,322,322, tag='yellow', fill='yellow', outline='white', width=2)
	canvas.create_rectangle(s,s,182,182, tag='green', fill='green', outline='white', width=2)
	canvas.create_text(300,160, text='Size of the board?', font='Arian 20 bold', fill='black', anchor='center', state=dis)
	
	def choice(value):
		game(win, map_sizes[value])
		canvas.destroy()
		
	canvas.tag_bind('red', '<Button-1>', lambda e: choice(2))
	canvas.tag_bind('yellow', '<Button-1>', lambda e: choice(1))
	canvas.tag_bind('green', '<Button-1>', lambda e: choice(0))
			
def game(win, map_size):
	width, height, mines = map_size
	#win.maxsize(width=width*k+s*2, height=height*k+s*2+42+6)
	#win.minsize(width=width*k+s*2, height=height*k+s*2+42+6)
	
	info = tkinter.Canvas(win, width=width*k+s*2, height=44, highlightthickness=0) #top pannel
	info.pack()
	canvas = tkinter.Canvas(win, width=width*k+s*2, height=height*k+s*2, highlightthickness=0) #game board
	canvas.pack()
	
	canvas.create_line(s-3,s-3,width*k+s+3,s-3, state=vis, fill='grey60')	#frame
	canvas.create_line(s-2,s-2,width*k+s+2,s-2, state=vis, fill='grey60')
	canvas.create_line(s-3,s-3,s-3,height*k+s+3, state=vis, fill='grey60')
	canvas.create_line(s-2,s-2,s-2,height*k+s+2, state=vis, fill='grey60')
	canvas.create_line(s-1,height*k+s+2,width*k+s+4,height*k+s+2, state=vis, fill='white')
	canvas.create_line(s-2,height*k+s+3,width*k+s+4,height*k+s+3, state=vis, fill='white')
	canvas.create_line(width*k+s+3,s-1,width*k+s+3,height*k+s+4, state=vis, fill='white')
	canvas.create_line(width*k+s+4,s-2,width*k+s+4,height*k+s+4, state=vis, fill='white')
	
	end = Count()
	mine_count = Count(place=info, coords=(s,2,60+s,42), dis=True, st=mines)
	cell_count = Count(st=width*height)
	if timer:
		time_count = Count(place=info, coords=((width*k+s*2)-s-60,2,(width*k+s*2)-s,42), dis=True, st=0, nul=True)
	smile = Smile(info, ((width*k+s*2)/2-20,2,(width*k+s*2)/2+20,42))
	
	map = []
	all_cells = []
	for r in range(height):
		for c in range(width):
			if height//3<r<(height//3)*2 and width//3<c<(width//3)*2: pass
			else: all_cells.append(r*width+c)
	random.shuffle(all_cells) #mix cells. First on the list of mines
	for r in range(height):
		row = []
		for c in range(width):
			if r*width+c in all_cells[:mines]: row.append([1,0,0])	#label: mine, open/close, flag/quest
			else: row.append([0,0,0])
		map.append(row)
	
	board = [] #cells
	for r in range(height):
		row = []
		for c in range(width):
			row.append(Cell(canvas, (c*k+s, r*k+s,(c+1)*k+s ,(r+1)*k+s)))
		board.append(row)
	
	def time_run():
		if end.count == 0:
			if win.focus_get():
				time_count.make('+')
			info.after(1000, time_run)
	
	def left_clicked(event): #press coords to address
		c = (event.x-s)//k	#s- indention error
		r = (event.y-s)//k
		if 0<=c<width and 0<=r<height: left_change(r,c)
	
	def right_clicked(event):
		c = (event.x-s)//k
		r = (event.y-s)//k
		if 0<=c<width and 0<=r<height: right_change(r,c)

	def left_change(r,c): #logic games
		if cell_count.count == width*height and timer: time_run()
		if map[r][c][1] == 0: #if close, open: delete cover, flag, quest, show opened
			[canvas.itemconfig(board[r][c].closed[i], state=hid) for i in range(len(board[r][c].closed))] #not show cover
			[canvas.itemconfig(board[r][c].flag[i], state=hid)   for i in range(len(board[r][c].flag))] #not show flag
			canvas.itemconfig(board[r][c].quest, state=hid) #not show question
			[canvas.itemconfig(board[r][c].opened[i], state=vis) for i in range(len(board[r][c].opened))] #shoq opened
			map[r][c][1] = 1 #opened
			cell_count.make('-')
			if cell_count.count == 0 and mine_count.count == 0:
				end.count = 1
				winer()
			if map[r][c][0]: #mine
				if end.count == 1: 
					[canvas.itemconfig(board[r][c].mine[i], state=vis) for i in range(len(board[r][c].mine))]
				else:
					[canvas.itemconfig(board[r][c].mine[i], state=vis) for i in range(len(board[r][c].mine))]
					canvas.itemconfig(board[r][c].opened[0], fill='red') #red cell, if explosion
					end.count = 1
					for rexp in range(height): #open all mines whitout flags
						for cexp in range(width):
							if map[rexp][cexp][0] == 1 and map[rexp][cexp][2] != 1:
								left_change(rexp,cexp)
					lose()
			else:
				mine_about = 0 #count mines
				for rmin in range(r-1,r+2):
					for cmin in range(c-1,c+2):
						if 0<=rmin<height and 0<=cmin<width and map[rmin][cmin][0]==1: mine_about += 1
				color = ('', 'blue', 'green', 'red', 'medium blue', 'red4', 'firebrick', 'blue4', 'brown') #цвета цифр
				if mine_about == 0: #no mines about, open free place
					for rnul in range(r-1,r+2):
						for cnul in range(c-1,c+2):
							if 0<=rnul<height and 0<=cnul<width: 
								left_change(rnul,cnul)
				elif mine_about <= 8: #draw mine count
					canvas.itemconfig(board[r][c].opened[1], text=('{}'.format(mine_about)), fill=color[mine_about])
				if map[r][c][2] == 1: #if flag
					mine_count.make('+') #return mine count
					cell_count.make('+') #return cell count
				

	def right_change(r,c):
		if map[r][c][1] == 0:	#if close, show flag
			if map[r][c][2] == 0:
				[canvas.itemconfig(board[r][c].flag[i], state=vis) for i in range(len(board[r][c].flag))]				
				map[r][c][2] = 1
				mine_count.make('-')
				cell_count.make('-')
				if cell_count.count == 0 and mine_count.count == 0:
					end.count = 1
					winer() #last cell? win!
			elif map[r][c][2] == 1: #show question, delete flag
				[canvas.itemconfig(board[r][c].flag[i], state=hid) for i in range(len(board[r][c].flag))]	
				canvas.itemconfig(board[r][c].quest, state=vis)
				map[r][c][2] = 2
				mine_count.make('+')
				cell_count.make('+')
			elif map[r][c][2] == 2: #delete question
				canvas.itemconfig(board[r][c].quest, state=hid)
				map[r][c][2] = 0
				
	def back_door_clicked(event):
		if back_door:
			c = (event.x-s)//k
			r = (event.y-s)//k
			if 0<=c<width and 0<=r<height:
				if map[r][c][0] == 0: left_change(r,c)
				else: right_change(r,c)

	canvas.bind('<Button-1>', left_clicked) #if canvas clicked
	canvas.bind('<Button-3>', right_clicked)
	canvas.bind('<Alt-Button-1>', back_door_clicked)
	
	def lose():
		canvas.create_text((width*k+s*2)/2,(height*k+s*2)/2, text='You LOSE!', font='Arian 20 bold', fill='red', anchor='center', state=dis)
		if hint:
			beg = (width*k+s*2)/2+30
			info.create_polygon(beg,22, beg+20,2, beg+20,12, beg+50,12, beg+50,32, beg+20,32, beg+20,42, fill='red', outline='black') #arrow
		smile.make('bad')
	
	def winer():
		canvas.create_text((width*k+s*2)/2,(height*k+s*2)/2, text='You WIN!', font='Arian 20 bold', fill='red', anchor='center', state=dis)
		if hint:
			beg = (width*k+s*2)/2+30
			info.create_polygon(beg,22, beg+20,2, beg+20,12, beg+50,12, beg+50,32, beg+20,32, beg+20,42, fill='red', outline='black')
		smile.make('good')
	
	def smile_clicked(event): #if in smile coords clicked
		x = event.x
		y = event.y
		if (width*k+s*2)/2-20<=x<(width*k+s*2)/2+20 and 2<=y<42:
			info.destroy()
			canvas.destroy()
			game(win, map_size) #new game, old dead
	
	info.bind('<Button-1>', smile_clicked)



hid = tkinter.HIDDEN #visible settings
vis = tkinter.NORMAL
dis = tkinter.DISABLED
k, s = 20, 10	#cell size, index
map_sizes = ((9,  9, 10), (16, 16, 40), (30, 16, 99))	#width, height, mines

window = tkinter.Tk()
window.title('Minesweeper')
window.resizable(0,0) #user cant change window size
start(window)

window.mainloop()

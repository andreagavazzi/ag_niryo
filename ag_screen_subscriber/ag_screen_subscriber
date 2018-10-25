#!/usr/bin/env python
import rospy
from time import sleep
from std_msgs.msg import String
from Tkinter import *


def callback(data):
    global lblvar
    lblvar.set(str(data.data))
    # rospy.loginfo('debug data: %s', str(data.data))
    sleep(3)
    lblvar.set('')


def listener():
    rospy.init_node('ag_output_screen', anonymous=False)
    rospy.Subscriber('ag_output', String, callback)


if __name__ == '__main__':

    print 'Program started, close the window to end'

    root = Tk()
    root.title('agScreen')

    # Etichetta >
    lbl0 = Label(root, text='> ')
    lbl0.config(font=("Arial", 30))
    lbl0.pack(side=LEFT)

    # Etichetta con testo (output screen)
    lblvar = StringVar()
    lbl1 = Label(root, textvariable=lblvar, width=25, anchor=W, pady=20)
    lbl1.config(font=("Arial", 30))
    lbl1.pack(side=LEFT)

    listener()

    root.mainloop()

    print 'Program terminated'

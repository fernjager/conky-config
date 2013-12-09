conky-config
============

Just a quick paste of my conky config. I've had this running on my Chromebook for a little over a year now, and have been happy with it. Here it is, enjoy!

![screenshot](https://github.com/fernjager/conky-config/raw/master/conky.png "Conky Screenshot")

```
#############################################
#  Robert's Conky configy
#
#

#maximum_width 100
own_window yes
own_window_transparent yes
own_window_type normal
own_window_hints undecorated,below,sticky,skip_taskbar,skip_pager
 
# Use double buffering (reduces flicker, may not work for everyone)
double_buffer yes

# fiddle with window
use_spacer yes
use_xft no

# Update interval in seconds
update_interval 3.0

# Minimum size of text area
# minimum_size 250 5

# Draw shades?
draw_shades no

# Text stuff
draw_outline no # amplifies text if yes
draw_borders no
uppercase no # set to yes if you want all text to be in uppercase

# Stippled borders?
stippled_borders 3

# border margins
border_margin 9

# border width
border_width 10

# Default colors and also border colors, grey90 == #e5e5e5
default_color grey # black

own_window_colour black # brown
own_window_transparent no

# Text alignment, other possible values are commented
#alignment top_left
 alignment top_right
#alignment bottom_left
#alignment bottom_right

# Gap between borders of screen and text
gap_x 10
gap_y 10

# stuff after 'TEXT' will be formatted on screen

TEXT
${color orange}WORLD TIME ${hr 2}$color
Local:            ${time %A %b %d %I:%M:%S %p}
UTC:	           ${utime %A %b %d %I:%M:%S %p} 

San Fancisco:     ${tztime America/Los_Angeles %A %b %d %I:%M:%S %p}
New York:         ${tztime America/New_York %A %b %d %I:%M:%S %p}
Taipei:           ${tztime Asia/Taipei %A %b %d %I:%M:%S %p}

${color orange}SYSTEM ${hr 2}$color
Processes: ${alignr}${color 85ADF5}$processes ($running_processes running)${color}
Uptime: ${alignr}${color 85ADF5}$uptime${color}

ACPI Battery: ${color 85ADF5}${battery sbs-4-000b}
${battery_bar sbs-4-000b 11,0}

${color orange}CPU ${hr 2}$color
${freq}MHz   Load: ${loadavg} 
  
CPU1: ${cpubar cpu1}
CPU2: ${cpubar cpu2}
${cpugraph cpu1 25,140 000000 ffffff} ${alignr}${cpugraph cpu2 25,140 000000 ffffff}

NAME             PID       CPU%      MEM%
${top name 1} ${top pid 1}   ${top cpu 1}    ${top mem 1}
${top name 2} ${top pid 2}   ${top cpu 2}    ${top mem 2}
${top name 3} ${top pid 3}   ${top cpu 3}    ${top mem 3}
${top name 4} ${top pid 4}   ${top cpu 4}    ${top mem 4}

${color orange}MEMORY / DISK ${hr 2}$color
RAM ${color orange}${alignr}$mem / $memmax $memperc%
${color white}${membar 10}${color}
ROOT   ${color orange}${alignr}${fs_used /} / ${fs_size /}  ${fs_used_perc /}% 
${color white}${fs_bar 10 /}${color}
ENTROPY${color orange}${alignr}${entropy_avail} / ${entropy_poolsize}  ${entropy_perc}% 
${color white}${entropy_bar 10}${color}

${color orange}NETWORK ( ${addr mlan0} / ${execi 3600 wget -O - http://66.172.10.98/ip.php | tail} ) ${hr 2}$color
Wireless signal: ${alignr}${wireless_link_qual mlan0}%

Down: $color${downspeed mlan0}/s ${alignr}Up: ${upspeed mlan0}/s
${downspeedgraph mlan0 25,140 000000 ff0000} ${alignr}${upspeedgraph mlan0 
25,140 000000 00ff00}$color
Total: ${totaldown mlan0} ${alignr}Total: ${totalup mlan0}

${color red}Port(s)${alignr}#Connections
$color In: ${tcp_portmon 1 32767 count} Out: ${tcp_portmon 32768 61000 count} ${alignr} All: ${tcp_portmon 1 65535 count}
${color red}Outbound Connection ${alignr} Remote Service/Port$color
${tcp_portmon 32768 61000 rhost 0} ${alignr} ${tcp_portmon 32768 61000 rservice 0}
${tcp_portmon 32768 61000 rhost 1} ${alignr} ${tcp_portmon 32768 61000 rservice 1}
${tcp_portmon 32768 61000 rhost 2} ${alignr} ${tcp_portmon 32768 61000 rservice 2}
${tcp_portmon 32768 61000 rhost 3} ${alignr} ${tcp_portmon 32768 61000 rservice 3}
${tcp_portmon 32768 61000 rhost 4} ${alignr} ${tcp_portmon 32768 61000 rservice 4}
${color red}Inbound Connection ${alignr} Local Service/Port$color
${tcp_portmon 1 32767 rhost 0} ${alignr} ${tcp_portmon 1 32767 lservice 0}
${tcp_portmon 1 32767 rhost 1} ${alignr} ${tcp_portmon 1 32767 lservice 1}
${tcp_portmon 1 32767 rhost 4} ${alignr} ${tcp_portmon 1 32767 lservice 4}
```

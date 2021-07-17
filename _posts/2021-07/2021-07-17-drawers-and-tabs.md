---
layout: post
title: "drawers and tabs"
date: 2021-07-17 11:54:49 +0530
categories: flutter
permalink: '/post/drawers-and-tabs'
---

Navigation in flutter using drawer and tabs 📱.

For navigation in an website there are links to be clicked. In case of mobile app these links are fine but using tabs or drawer for navigation makes ui more friendly and cool. Flutter provides both of these feature as widgets.

Drawer is the menu that generally comes out when clicking on a hamburger button on the left. To use drawer the `Drawer` widget has to be used and it has to be used inside Scaffold widget as a value for drawer method. Inside the Drawer widget Listview or Column widget can be used to display navigation links. Using ListView is a better option as it helps to scroll when there are many links. Also to add a header like app logo at the top of drawer DrawerHeader widget has to be used.

Tabs are another good option when there are less number of navigation. For tabs `DefaultTabController` and `TabController` widgets are there. The DefaultTabController takes length as an argument. Various tabs can be inserted inside TabBar widget in a list in tabs argument. For a single tab Tab widget can be used inside which Text or Icon can be diplayed. To display different screens upon clicking on different tabs TabBarView view is used. The children inside this widget will diplay the respective tabs mentioned in TabBar tabs argument list. 
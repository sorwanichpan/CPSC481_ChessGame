#########################################################################
# CPSC 481: Assignment 1
# Date: 9/22/14
# Authors:  Sorasit Wanichpan (ADD YOUR NAMES)
#           Scott Blomquist
# Changelog:
# 9/22/14 (Sorasit) -- Added ASCII Chessboard (Visual Representation)
#                   -- Added King valid movement rules
#                   -- Added Rook valid movement rules
# 9/23/14 (Sorasit) -- Integrated the Knight sample from easyAI with Chess 
#                   -- Added an uncomfortable amount of comments
# 9/26/14 (Stetzko) -- Added DictTT for transposition tables to speed it up
#                   -- table = DictTT() to assign the transpostion tables
#                   -- Changed the ai_algo = Negamax(11) to 
#                      ai_algo = Negamax(2, tt = table) to speed up the game
#                      the 2 represents how many moves it will check ahead and
#                      for some reason if you go higher than 2 it will not work.
#                   -- In the possible moves method I added a comment that will
#                      help us better understand our logic on the AI
#                   -- Also added the other two positions just for the output of
#                      the board
# 9/29/14 (Henry)   -- A Black King has random movements
#                   -- White King has an advance movement system to follow the black king.
#                   --   Still needs to work on keep 1 distant away from the black king.
#                   -- random king and rook placements.
# 9/29/14 (Sorasit) -- Added the Rook piece into the game space
# 9/30/14 (Henry)   -- Great news:
#                   -- White king does not hump the black king anymore
#                   -- Black king needs the rook so that we have a proper "dangerspot"
#                   --      Black king is currently roaming around freely, (can't) implement checkmate because here is no rook.
#                   --      Still need to do the delay algorithm.
#                   -- Note:the current pieces placement is so that the white wins in one move
#                   --      I used the rook to corner the black king, the rook does not make the black king in check.
#                   --      p.s. Player 2 (black king) loses because it cannot make any valid moves
# 10/2/2014         -- Fixed the ROOKD movements and Generated new (hopefully correct) Rook movements
#                   -- Changed the game max from 1000 to 10 for debugging
# 
# 10/3/2014(Scott B)-- Changed the how the black kings position was defined to: 'player[1].pos[0]' 
#                      to be consistent with the white pieces name structure (makes it simpler to access either players king piece)
#                   -- Implemented kingInCheck() function that returns a bool value based on current piece positions on the board
#                   -- Added an enumeration class to label pieces more easily
#                   -- Cleaned up some commenting
#                   -- Put check conditions into the make_move and possible_move functions
#                   -- added print() statements to tell the user if the game was ended through stalemateor through checkmate.
# 10/3/2014(Sorasit) -- Started work on Rook movement
#                    --     The rook can now move horizontally or vertically as intended
#                    --     Rook no longer kamakizes off the baord
#                    --     Split the possible Rook moves into two categories (For column and Rows respectively)
#                    --     Added a checking loop that looks for any piece within that row or column (Currently not working)
#                    -- Added the unicode piece representation
#                    -- Reoriented the chessboard (nothing should be affected, just a visual representation)
#                    -- Added OS module, every time a new move is made, the screen will clear then print out a new board
#                    --     Check the show module
#                    --     Also added sleep(1) so I can sanely watch the game being played
#                    -- TODO: Make the rook look for the shortest possible way to check the king (based off shortest distance formula)
# 10/5/2014(Sorasit) -- Added preliminary command line tools
#					 -- 	added N_Turn argument
#					 --     added verbose, (Currently not working)
#					 --     Use -h or --help for arguments
#				     -- Moved changelog over to the README.md instead
#				
#
#
#
#########################################################################

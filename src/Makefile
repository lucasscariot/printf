# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: lscariot <marvin@42.fr>                    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2016/01/22 09:44:59 by lscariot          #+#    #+#              #
#    Updated: 2016/09/15 23:22:34 by lscariot         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #


NAME	= printf

LINK	= ../printf

CC		= clang

S_DIR	=

O_DIR	=

I_DIR	=

FLAGS	= -Wall -Wextra -Werror $(I_DIR) $(LIBS_DIR)

FILES	=   main.c

LIBS_F	= ./libft/libft.a

SRC		= $(addprefix $(S_DIR),$(FILES))

OBJS	= $(addprefix $(O_DIR),$(FILES:.c=.o))

LIBS	= $(addprefix -L. -l,$(LIBS_F))

RM		= rm -f

all: 		$(NAME)

$(NAME): 	$(OBJS)
	@echo ""
	@make -C libft
	@$(CC) $(FLAGS) -I./includes $(LIBS_F) $^ -o $(LINK)
	@echo "\033[32m$(NAME) created.\033[0m"

$(O_DIR)%.o:		$(S_DIR)%.c
	@$(CC) $(FLAGS) -I./includes -c $< -o $@
	@echo "\033[33m.\033[0m\c"

clean:
	@$(RM) $(OBJS)
	@make -C libft clean

fclean: 	clean
	@$(RM) $(LINK)
	@make -C libft fclean
	@echo "\033[31m$(NAME) cleaned.\033[0m"

re:			fclean all
	@make clean

.PHONY: re clean fclean all

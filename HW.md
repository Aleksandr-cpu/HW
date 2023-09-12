Здесь изменения!

# Параметр help.autocorrect

Неправильный набор команды приводит к вот такому результату:
* $ git chekcout master
* git: 'chekcout' is not a git command. See 'git --help'.
* Did you mean this?
* checkout

Система Git вежливо пытается выяснить, что вы имели в виду, но никаких действий не
предпринимает. Если же присвоить параметру help.autocorrect значение 1, Git автоматически запустит команду, если она является единственным подходящим вариантом:
$ git chekcout master
WARNING: You called a Git command named 'chekcout', which does not exist.
Continuing under the assumption that you meant 'checkout'
in 0.1 seconds automatically...
Учитывайте, что запись 0.1 seconds (0,1 секунды) в переменной help.autocorrect
на самом деле соответствует десятой части секунды и представляет собой целое
число. Если присвоить этой переменной значение 50, система Git даст вам 5 секунд
на размышление и только после этого выполнит скорректированную команду.
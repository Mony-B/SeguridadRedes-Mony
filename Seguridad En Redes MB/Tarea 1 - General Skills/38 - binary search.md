# DESCRIPCIÓN:

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/19/challenge.zip)

`ssh -p 49402 ctf-player@atlas.picoctf.net`

Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

Hints

Have you ever played hot or cold? Binary search is a bit like that.

You have a very limited number of guesses. Try larger jumps between numbers!

The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?

# SOLUCIÓN:
#### picoCTF{g00d_gu355_1597707f}

```
mony@Mony:/mnt/c/Users/Usuario$ ssh -p 49402 ctf-player@atlas.picoctf.net
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@atlas.picoctf.net's password:
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 5000
Lower! Try again.
Enter your guess: 500
Lower! Try again.
Enter your guess: 499
Lower! Try again.
Enter your guess: 480
Lower! Try again.
Enter your guess: 300
Lower! Try again.
Enter your guess: 10
Lower! Try again.
Enter your guess: 2
Congratulations! You guessed the correct number: 2
Here's your flag: picoCTF{g00d_gu355_1597707f}
Connection to atlas.picoctf.net closed.
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/
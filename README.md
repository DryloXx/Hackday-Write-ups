# Write-up Pokémons Hackday

![image](https://user-images.githubusercontent.com/96259302/163978275-45e12caa-add1-45b6-a7c8-802514b1a3fa.png)

For this challenge, we have a png file, named here “pokedex.png”.
First thing we do is check the metadatas of this file, and that’s we find :

![image](https://user-images.githubusercontent.com/96259302/163978444-51532e8a-f5ff-44f7-80f2-d49ed3a49489.png)


Now we know that our file isn’t a simple png, but an animated png, AKA apng. Next, I’ve tried a lot of things on this file, like disassemble it and look deeper in the images that are in the apng file, but nothing very interesting...

After several hours of tearing my hair out, I realized that the solution maybe wasn’t in the png files inside de apng. I tried more things on the apng file directly, and I read about the structure of an apng file, from which I didn’t knew a lot.
I leaned that the apng structure is a succession of fcTL and fDAT chunks, which is what we probably need to focus on. I managed to find this website : https://fotoforensics.com
 
Next thing is to upload the apng file into the website and see what it will find.

If we go in the “Strings” section in the analysis section, we can see that the website has separated all the chunks. If we look in the fcTL chunks, we can see that most of the time, one letter stands out from the rest. Now, I tried to concatenate all the letters that I manage to get from these chunks.

![image](https://user-images.githubusercontent.com/96259302/163978714-9919d4a9-3ef4-480a-a968-8e372d292ead.png)

I first found this :

![image](https://user-images.githubusercontent.com/96259302/163978750-1128399f-2c90-4de9-baf8-b1addfa1e93f.png)

I putted blank spaces when the chunk was empty, so I thought that some letters were missing at these emplacements. I tried to guess all the missing letters to finally get the flag :

![image](https://user-images.githubusercontent.com/96259302/163978793-d9936afa-0101-4981-9088-c107dfdccf6c.png)

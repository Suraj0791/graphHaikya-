

### Pattern 1 — BFS / Simple Traversal



1. `q.push({nr, nc});`
2. `grid[nr][nc] = '0';`



Bhai iss code block mein bhi **un dono lines ke order se ratti bhar farq nahi padta!**

Chahe tu code aise likh de:

cpp

if (nr >= 0 && nr < n && nc >= 0 && nc < m && grid[nr][nc] == '1') {

    q.push({nr, nc});     // Pehle push kiya

    grid[nr][nc] = '0';   // Phir visited (0) kiya

}

Ya fir aise likh de:

cpp

if (nr >= 0 && nr < n && nc >= 0 && nc < m && grid[nr][nc] == '1') {

    grid[nr][nc] = '0';   // Pehle visited (0) kiya

    q.push({nr, nc});     // Phir push kiya

}

**Dono 1000% correct hain aur dono ekdam same speed se chalenge.**

Mera "CRITICAL" likhne ka matlab inka aapas ka order nahi tha. Mera matlab tha ki **"bhai bhoolna mat ki in dono ko yahi, is 'if' condition ke andar hi sath mein likhna hai!"**

Bas iss `if` bracket ke andar hone chahiye dono. Upar kaunsa hai, neeche kaunsa hai, CPU ko usse ghanta farq nahi padta! Bindass in dono mein se jo order yaad aaye likh dena.






***BHAI EK BAAT YAAD RKHO U PUSH IN QUEUE AS SOON AS U PUSH THAPPA MAARD O MARK AS VISITED KA PUSH KE BAAD , VVVI CHIZ KI TM PEHGLE THAPPA MAARKE PUSH KR SKTE HO JUST NEXT LINE ORDER DEOSNT MATETR BUT WHAT MATETRS KI YE DONO CHIZ ADJANCE THONI CHAIYE 


***ND THIS WE ARE DOING TWO PLACES EK JAB BFS M ENTRY KRTE H BRO JAB SMJHO SOURCE KO DAALTE H QUEUS M TAB THAPA MAARO VISITED KA equals to zero krde nd fir ek jab while loop ke andar jab fir se new nr nc ko pusbh krte h queu m to fir se thappa amrde 

are mtlb kul mila ke kya smjha ??? dono adjance hoga ??

ab sun ?? baaki plzz kch bhi yaad mt rkhna bfs m ki kab kya krna tha kis case me rro aayega kyu yaad rkhna wo ki agar visted mark nhi kiya push ke time nd pop ke time kiya to memoy limit excedded aaygea mle ram 100% used 
ae bhai fuck all thsi foget 


PSEUDO CODE

Ekdum sahi baat boli bhai! Bura wala yaad hi kyu rakhna jab seedha bulletproof raasta pata ho. Faltu ka kachra dimag se nikal do.

Bas **BFS Grid** ke liye ye sunehra Pseudo-Code dimaag mein print kar lo. Iske alawa kabhi kuch mat sochna!



### 🏆 THE BULLETPROOF BFS TEMPLATE (Grid)

**Mantra:** "Dekha -> Push Kiya -> Thappa Maara"

```
void bfs(int r, int c, grid) {
    queue q;
    
    // 1️⃣ STARTING NODE: Dekha -> Push -> Thappa
    q.push({r, c});
    grid[r][c] = '0'; // (Thappa!)
    
    while (!q.empty()) {
        auto curr = q.pop();
        
        // 2️⃣ PADOSI CHECK
        for (4 directions) {
            int nr = ...
            int nc = ...
            
            if (Valid Boundaries && Zameen Mili) {
                // 3️⃣ NAYA NODE: Dekha -> Push -> Thappa
                q.push({nr, nc});
                grid[nr][nc] = '0'; // (Thappa!)
            }
        }
    }
}

```



**Sirf 2 jagah Push hota hai, aur wahi Thappa lagta hai:**

1. Ek baar `while` loop shuru hone se theek pehle (Pehle Node ke liye).
2. Ek baar `for` loop ke andar (Padosiyon ke liye).

Jahan Push dikhega, uski agli hi line par Visit/Thappa dikhega. Bas yahi ek sachai hai, isko notes mein likh le aur bhagwaan ka naam leke aage badh! 🚀









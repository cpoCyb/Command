
# Network command 

## Windows : 

Windows command to check the opening of a port from PowerShell : 

```bash
  Test-NetConnection -Port 80 X.X.X.X
```

## Linux : 

Scan the network via NMAP :

```bash
  nmap -sV -sC X.X.X.X
```

Avec ça, tu seras blacklisté directement par n’importe quel firewall ou WAF, oublie

```bash
  nmap -A X.X.X.X
```

Ça fait un ping et ça scanne les ports 80 et 443, soit, les ports HTTP et HTTPS. C’est un peu plus discret, mais ça reste un scan.
```bash
  nmap -PS X.X.X.X
```

On oublie, tu fais uniquement la requête SYN, ce qui est peu habituel, donc tu risques d’être grillé.

```bash
  nmap -sS X.X.X.X
```

Ça, c’est déjà mieux ; tu utilises la librairie de ton système donc moins détectable.

```bash
  nmap -sT X.X.X.X
```

Pour tenter de récupérer les versions des services exposés, c’est un peu plus discret, mais ça reste un scan. Avec ça, si les versions sont obsolètes, tu peux aller chercher des CVE pour les outils et versions correspondantes.

```bash
  nmap -sV X.X.X.X
```

Pour la détection des OS, pas très précis, autant éviter.

```bash
  nmap -O X.X.X.X
```

Ça scanne tous les ports, il y en a 65536. Autant envoyer un mail pour dire que tu fais un scan.

```bash
  nmap -p- X.X.X.X
```

Paranoïde - Très lent et discret. Utilisé pour éviter la détection par les systèmes de détection d'intrusion (IDS).

```bash
  nmap -T0 X.X.X.X
```

Sneaky - Lent. Plus discret mais toujours relativement lent.

```bash
  nmap -T1 X.X.X.X
```

Gentil - Modérément lent. Réduis la vitesse du scan pour minimiser les détections.

```bash
  nmap -T2 X.X.X.X
```

Normal - Vitesse normale. C’est le réglage par défaut.

```bash
  nmap -T3 X.X.X.X
```

Agressive - Plus rapide. Utilise une approche plus agressive qui peut attirer l’attention.

```bash
  nmap -T4 X.X.X.X
```

Insane - Rapide et très agressif. Les cibles peuvent être surchargés, généralement repérée rapidement.

```bash
  nmap -T5 X.X.X.X
```

Scan UDP – Lent mais nécessaire, il explore les profondeurs des services UDP comme DNS et DHCP.

```bash
  nmap -sU X.X.X.X
```

---
title: "Ressourcencompiler: Fehler RW2002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2002"
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Fehler RW2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verarbeitungsfehler  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  **Zugriffstastentyp erforderlich \(ASCII oder VIRTKEY\)**  
  
     Das type\-Feld in der ACCELERATORS\-Anweisung muss entweder den **ASCII**\-Wert oder den **VIRTKEY**\-Wert enthalten.  
  
2.  **BEGIN in Zugriffstastentabelle erwartet**  
  
     Das **BEGIN**\-Schlüsselwort muss unmittelbar auf das **ACCELERATORS\-**Schlüsselwort folgen.  
  
3.  **BEGIN in Dialogfeld erwartet**  
  
     Das BEGIN\-Schlüsselwort muss unmittelbar auf das DIALOG\-Schlüsselwort folgen.  
  
4.  **BEGIN in Menü erwartet**  
  
     Das **BEGIN**\-Schlüsselwort muss unmittelbar auf das MENU\-Schlüsselwort folgen.  
  
5.  **BEGIN in RCData erwartet**  
  
     Das **BEGIN**\-Schlüsselwort muss unmittelbar auf das RCDATA\-Schlüsselwort folgen.  
  
6.  **BEGIN\-Schlüsselwort in Zeichenfolgentabelle erwartet**  
  
     Das **BEGIN**\-Schlüsselwort muss unmittelbar auf das **STRINGTABLE**\-Schlüsselwort folgen.  
  
7.  **Zeichenfolgenkonstanten können nicht wiederverwendet werden**  
  
     In einer STRINGTABLE\-Anweisung wird zweimal derselbe Wert verwendet.  Stellen Sie sicher, dass keine überlappenden dezimalen und hexadezimalen Werte verwendet werden.  Jede ID in einer **STRINGTABLE** muss eindeutig sein.  Um größte Effizienz zu erzielen, verwenden Sie aufeinander folgende Konstanten, die bei einem Vielfachen von 16 beginnen.  
  
8.  **Steuerzeichen außerhalb des gültigen Bereichs \[^A \- ^Z\]**  
  
     Die ACCELERATORS\-Anweisung enthält ein ungültiges Steuerzeichen.  Das auf das Zirkumflexzeichen \(^\) folgende Zeichen muss zwischen A und Z inklusive liegen.  
  
9. **Leere Menüs nicht zulässig**  
  
     Das END\-Schlüsselwort trat auf, ohne dass Menüpunkte in der MENU\-Anweisung definiert wurden.  Es werden keine leeren Menüs vom Ressourcencompiler zugelassen.  Stellen Sie sicher, dass keine offenen Anführungszeichen innerhalb der MENU\-Anweisung verwendet werden.  
  
10. **END in Dialogfeld erwartet**  
  
     Das **END**\-Schlüsselwort muss sich am Ende einer DIALOG\-Anweisung befinden.  Stellen Sie sicher, dass keine offenen Anführungszeichen aus der vorangegangenen Anweisung übrig geblieben sind.  
  
11. **END in Menü erwartet**  
  
     Das **END**\-Schlüsselwort muss sich am Ende einer MENU\-Anweisung befinden.  Stellen Sie sicher, dass keine offenen Anführungszeichen oder BEGIN\-Anweisungen bzw. END\-Anweisungen ohne Entsprechungen verwendet werden.  
  
12. **Komma in Zugriffstastentabelle erwartet**  
  
     Ein Komma zwischen dem event\-Feld und dem idvalue\-Feld in der ACCELERATORS\-Anweisung ist für den Ressourcencompiler erforderlich.  
  
13. **Steuerelement\-Klassenname erwartet**  
  
     Das `class`\-Feld einer **CONTROL**\-Anweisung innerhalb einer **DIALOG**\-Anweisung muss einen der folgenden Typen aufweisen: BUTTON, COMBOBOX, EDIT, LISTBOX, SCROLLBAR, STATIC oder benutzerdefiniert.  Stellen Sie sicher, dass die Klasse richtig geschrieben ist.  
  
14. **Name eines Schriftstils erwartet**  
  
     Das *typeface*\-Feld der **FONT**\-Option innerhalb der DIALOG\-Anweisung muss eine ASCII\-Zeichenfolge enthalten, die in Anführungszeichen eingeschlossen ist.  In diesem Feld wird der Namen einer Schriftart festgelegt.  
  
15. **ID\-Wert für Menüelement erwartet**  
  
     Die MENU\-Anweisung muss ein *menuID*\-Feld enthalten, in dem der Name oder die Nummer, durch den bzw. die die Menüressource identifiziert wird, angegeben wird.  
  
16. **Menüzeichenfolge erwartet**  
  
     Jede MENUITEM\-Anweisung und jede POPUP\-Anweisung muss ein text\-Feld mit einer Zeichenfolge in doppelten Anführungszeichen enthalten, durch die der Name des Menüelements oder des Popupmenüs angegeben wird.  Für die MENUITEM SEPARATOR\-Anweisung ist keine Zeichenfolge in Anführungszeichen erforderlich.  
  
17. **Numerischer Befehlswert erwartet**  
  
     Ein numerisches idvalue\-Feld in der ACCELERATORS\-Anweisung wurde erwartet.  Stellen Sie sicher, dass eine \#define\-Konstante verwendet wurde, um den Wert anzugeben, und dass die Konstante richtig geschrieben ist.  
  
18. **Numerische Konstante in Zeichenfolgentabelle erwartet**  
  
     Eine numerische Konstante, die in einer \#define\-Anweisung definiert wird, muss unmittelbar auf das BEGIN\-Schlüsselwort in einer STRINGTABLE\-Anweisung folgen.  
  
19. **Numerischer Schriftgrad erwartet**  
  
     Das *pointsize*\-Feld der **FONT**\-Option innerhalb der DIALOG\-Anweisung muss einen Ganzzahlwert für den Schriftgrad enthalten.  
  
20. **Numerische Dialogfeldkonstante erwartet**  
  
     Für eine DIALOG\-Anweisung sind Ganzzahlwerte für die Felder x, y, width und height erforderlich.  Stellen Sie sicher, dass diese Werte nach dem **DIALOG**\-Schlüsselwort enthalten sind und dass sie nicht negativ sind.  
  
21. **Zeichenfolge in STRINGTABLE erwartet**  
  
     Eine Zeichenfolge wird nach jedem stringid\-Wert in einer STRINGTABLE\-Anweisung erwartet.  
  
22. **Zeichenfolgen\- oder Konstanten\-Zugriffstastenbefehl erwartet**  
  
     Der Ressourcencompiler konnte nicht feststellen, welche Art von Taste als Zugriffstaste eingerichtet werden soll.  Das event\-Feld in der ACCELERATORS\-Anweisung ist möglicherweise ungültig.  
  
23. **Zahl als ID erwartet**  
  
     Es wurde eine Zahl für das id\-Feld einer Steuerelementanweisung innerhalb der DIALOG\-Anweisung erwartet.  Stellen Sie sicher, dass eine Zahl oder eine \#define\-Anweisung als Steuerelement\-ID angegeben wurde.  
  
24. **Zeichenfolge in Anführungszeichen in Dialogklasse erwartet**  
  
     Das `class`\-Feld der **CLASS**\-Option innerhalb der DIALOG\-Anweisung muss eine ganze Zahl oder eine Zeichenfolge, die in Anführungszeichen eingeschlossen ist, enthalten.  
  
25. **Zeichenfolge in Anführungszeichen im Dialogtitel erwartet**  
  
     In der **DIALOG**\-Anweisung muss das `captiontext`\-Feld der CAPTION\-Option eine in doppelte Anführungszeichen eingeschlossene ASCII\-Zeichenfolge enthalten.  
  
26. ****Datei nicht gefunden:** Dateiname**  
  
     Die in der Befehlszeile des Ressourcencompilers angegebene Datei wurde nicht gefunden.  Überprüfen Sie, ob die Datei in ein anderes Verzeichnis verschoben wurde und ob der Dateiname oder der Pfad korrekt eingegeben wurde.  Nach Dateien wird unter Verwendung der **INCLUDE**\-Umgebungsvariablen oder der Einstellung für Visual Workbench, sofern vorhanden, gesucht.  
  
27. **Schriftartnamen müssen Ordnungszahlen sein**  
  
     Das *pointsize*\-Feld in der FONT\-Anweisung muss eine ganze Zahl enthalten, keine Zeichenfolge.  
  
28. **Ungültige Zugriffstaste**  
  
     Ein event\-Feld in der ACCELERATORS\-Anweisung wurde nicht erkannt oder war länger als zwei Zeichen.  
  
29. **Ungültiger Zugriffstastentyp \(ASCII oder VIRTKEY\)**  
  
     Das type\-Feld in der ACCELERATORS\-Anweisung muss entweder den **ASCII**\-Wert oder den **VIRTKEY**\-Wert enthalten.  
  
30. **Ungültiges Steuerzeichen**  
  
     Die ACCELERATORS\-Anweisung enthält ein ungültiges Steuerzeichen.  Ein gültiges Steuerzeichen besteht aus \(nur\) einem Buchstaben, der auf ein Zirkumflexzeichen \(^\) folgt.  
  
31. **Ungültiger Steuerelementtyp**  
  
     Bei jeder Steuerelementanweisung in einer **DIALOG**\-Anweisung muss es sich um eine der folgenden handeln: **CHECKBOX**, **COMBOBOX**, **CONTROL**, **CTEXT**, **DEFPUSHBUTTON**, **EDITTEXT**, **GROUPBOX**, **ICON**, **LISTBOX**, **LTEXT**, **PUSHBUTTON**, **RADIOBUTTON**, **RTEXT** oder **SCROLLBAR**.  Stellen Sie sicher, dass diese Steuerelementanweisungen richtig geschrieben sind.  
  
32. **Ungültiger Typ**  
  
     Der Ressourcentyp gehört nicht zu den in der Datei WINDOWS.h definierten Typen.  
  
33. **Textzeichenfolge oder Ordnungszahl im Steuerelement erwartet**  
  
     Das *text*\-Feld einer **CONTROL**\-Anweisung innerhalb einer **DIALOG**\-Anweisung muss entweder eine Textzeichenfolge oder einen Ordnungszahlverweis auf den Steuerelementtyp enthalten.  Wenn eine Ordnungszahl verwendet wird, stellen Sie sicher, dass eine \#define\-Anweisung für das Steuerelement zur Verfügung steht.  
  
34. **Fehler bei Klammern**  
  
     Stellen Sie sicher, dass alle offenen Klammern in der **DIALOG**\-Anweisung geschlossen wurden.  
  
35. **Unerwarteter Wert in RCData**  
  
     Bei den *raw\-data*\-Werten in der RCDATA\-Anweisung muss es sich um ganze Zahlen oder Zeichenfolgen, die jeweils durch ein Komma voneinander getrennt sind, handeln.  Stellen Sie sicher, dass kein Komma oder Anführungszeichen um eine Zeichenfolge ausgelassen wurde.  
  
36. **Unbekannter Menüuntertyp**  
  
     Das *item\-definition*\-Feld der MENU\-Anweisung kann nur MENUITEM\-Anweisungen und POPUP\-Anweisungen enthalten.
---
title: 'Ressourcencompiler: Fehler RW2002 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2002
dev_langs: C++
helpviewer_keywords: RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db322791c3804f387c452b3839260826585a2e30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2002"></a>Ressourcencompiler: Fehler RW2002
Fehler beim Analysieren  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  **Zugriffstastentyp erforderlich (ASCII oder VIRTKEY)**  
  
     Das `type` -Feld der **ACCELERATORS** -Anweisung muss entweder den ASCII- oder den VIRTKEY-Wert enthalten.  
  
2.  **BEGIN in Zugriffstastentabelle erwartet**  
  
     Das **BEGIN** -Schlüsselwort muss direkt auf das **ACCELERATORS** -Schlüsselwort folgen.  
  
3.  **BEGIN in Dialogfeld erwartet.**  
  
     Die **beginnen** -Schlüsselwort muss unmittelbar folgen der **Dialogfeld** Schlüsselwort.  
  
4.  **BEGIN in Menü erwartet.**  
  
     Das **BEGIN** -Schlüsselwort muss direkt auf das **MENU** -Schlüsselwort folgen.  
  
5.  **BEGIN in RCData erwartet.**  
  
     Das **BEGIN** -Schlüsselwort muss direkt auf das **RCDATA** -Schlüsselwort folgen.  
  
6.  **BEGIN-Schlüsselwort in Zeichenfolgentabelle erwartet**  
  
     Die **beginnen** -Schlüsselwort muss unmittelbar folgen der **STRINGTABLE** Schlüsselwort.  
  
7.  **Zeichenfolgenkonstanten kann nicht erneut verwendet werden.**  
  
     Sie verwenden den gleichen Wert zweimal in eine **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimaler und hexadezimaler Werte. Jede ID in einer **STRINGTABLE** muss eindeutig sein. Verwenden Sie für maximaler Effizienz zusammenhängende Konstanten, die auf ein Vielfaches von 16 zu starten.  
  
8.  **Steuerzeichen außerhalb des gültigen Bereichs [^ A - ^ Z]**  
  
     Ein Steuerzeichen in der **ACCELERATORS** -Anweisung ist ungültig. Das auf das Caretzeichen (**^**) folgende Zeichen muss zwischen A und Z (einschl.) liegen.  
  
9. **Leere Menüs nicht zulässig**  
  
     Ein **END** Schlüsselwort angezeigt wird, bevor alle Menüelemente in definiert sind die **Menü** Anweisung. Der Ressourcencompiler lässt sich nicht auf leere Menüs aus. Stellen Sie sicher, dass Sie keine öffnenden Anführungszeichen innerhalb der **Menü** Anweisung.  
  
10. **Ende, die im Dialogfeld "erwartet**  
  
     Die **END** Schlüsselwort muss erfolgen, am Ende einer **Dialogfeld** Anweisung. Stellen Sie sicher, dass keine offenen Anführungszeichen aus der vorherigen Anweisung übrig.  
  
11. **END in Menü erwartet.**  
  
     Das **END** -Schlüsselwort muss am Ende einer **MENU** -Anweisung stehen. Stellen Sie sicher, dass keine öffnenden Anführungszeichen oder nicht übereinstimmende Paare von **BEGIN** - und **END** -Anweisungen vorhanden sind.  
  
12. **Komma in Zugriffstastentabelle erwartet**  
  
     Der Ressourcencompiler erfordert ein Komma zwischen dem Feld `event` und dem Feld *idvalue* in der **ACCELERATORS** -Anweisung.  
  
13. **Erwartete Steuerelementname-Klasse**  
  
     Die `class` Feld eine **Steuerelement** -Anweisung in der **Dialogfeld** -Anweisung muss einen der folgenden Typen sein: Schaltfläche, COMBOBOX, EDIT, LISTBOX, SCROLLBAR, STATIC "," oder eine benutzerdefinierte. Stellen Sie sicher, dass die Klasse richtig geschrieben ist.  
  
14. **Name einer Schriftart erwartet**  
  
     Das Feld *typeface* der FONT-Option in der **DIALOG** -Anweisung muss eine ASCII-Zeichenfolge in doppelten Anführungszeichen sein. Dieses Feld gibt den Namen einer Schriftart an.  
  
15. **Erwarteter ID-Wert für "MenuItem"**  
  
     Die **MENU** -Anweisung muss ein *menuID* -Feld aufweisen, in dem der Name oder die Nummer angegeben ist, der bzw. die die Menüressource identifiziert.  
  
16. **Menüzeichenfolge erwartet**  
  
     Jede **MENUITEM** - und **POPUP** -Anweisung muss ein *Text* -Feld enthalten. Hierbei handelt es sich um eine Zeichenfolge in doppelten Anführungszeichen, die den Namen des Menüelements oder Popupmenüs angibt. Ein **"MenuItem" TRENNZEICHEN** Anweisung erfordert keine Zeichenfolge in Anführungszeichen.  
  
17. **Numerische Befehlswert erwartet**  
  
     Der Ressourcencompiler hat ein numerischer erwartet *Idvalue* -Feld in der **ZUGRIFFSTASTEN** Anweisung. Stellen Sie sicher, dass Sie verwendet haben, eine `#define` Konstante zum Angeben des Werts und dass die Konstante richtig geschrieben ist.  
  
18. **Numerische Konstante erwartet in Zeichenfolgentabelle**  
  
     Eine in einer `#define` -Anweisung definierte numerische Konstante muss direkt auf das **BEGIN** -Schlüsselwort in einer **STRINGTABLE** -Anweisung folgen.  
  
19. **Numerische Punktgröße erwartet**  
  
     Das Feld *pointsize* der Option FONT in der Anweisung **DIALOG** muss ein ganzzahliger Punktgrößenwert sein.  
  
20. **Numerische Dialogfeldkonstante erwartet**  
  
     Ein **Dialogfeld** Anweisung erfordert ganzzahlige Werte für die *X, y, Breite*, und *Höhe* Felder. Stellen Sie sicher, dass diese Werte nach enthalten die **Dialogfeld** -Schlüsselwort und nicht negativ sind.  
  
21. **Erwartete Zeichenfolge in STRINGTABLE**  
  
     Nach jedem *stringid* -Wert in einer **STRINGTABLE** -Anweisung wird eine Zeichenfolge erwartet.  
  
22. **Erwartete Zeichenfolgen- oder Konstantenzugriffstaste**  
  
     Der Ressourcencompiler konnte nicht bestimmen, welche Art von Schlüssel für die Zugriffstaste eingerichtet wurde. Das `event` -Feld in der **ACCELERATORS** -Anweisung ist möglicherweise ungültig.  
  
23. **Zahl erwartet als ID**  
  
     Erwarten eine Zahl für die `id` -Feld der Control-Anweisung in der **Dialogfeld** Anweisung. Stellen Sie sicher, dass eine Zahl oder `#define` -Anweisung für die Steuerelement-ID.  
  
24. **Zeichenfolge in Anführungszeichen erwartet in Dialogklasse**  
  
     Das `class` -Feld der CLASS-Option in der **DIALOG** -Anweisung muss eine ganze Zahl oder eine Zeichenfolge, die in doppelte Anführungszeichen eingeschlossen ist, enthalten.  
  
25. **Zeichenfolge in Anführungszeichen erwartet in Dialogfeldtitel**  
  
     Das `captiontext` -Feld der CAPTION-Option in der **DIALOG** -Anweisung muss eine ASCII-Zeichenfolge in doppelten Anführungszeichen sein.  
  
26. **Datei wurde nicht gefunden: Dateiname**  
  
     Die in der Befehlszeile des Ressourcencompilers angegebene Datei wurde nicht gefunden. Überprüfen Sie, ob die Datei in ein anderes Verzeichnis verschoben wurde und ob der Dateiname und der Pfad korrekt eingegeben wurden. Dateien werden durchsucht, für die Verwendung der **INCLUDE** -Umgebungsvariablen oder der Einstellung für Visual Workbench, falls verfügbar.  
  
27. **Schriftartnamen müssen Ordnungszahlen sein.**  
  
     Die *Pointsize* Feld in der Schriftart-Anweisung muss eine ganze Zahl, keine Zeichenfolge sein.  
  
28. **Ungültige Zugriffstaste**  
  
     Ein `event` -Feld in der **ACCELERATORS** -Anweisung wurde nicht erkannt oder ist mehr als zwei Zeichen lang.  
  
29. **Ungültiger Zugriffstastentyp (ASCII oder VIRTKEY)**  
  
     Das `type` -Feld der **ACCELERATORS** -Anweisung muss entweder den ASCII- oder den VIRTKEY-Wert enthalten.  
  
30. **Ungültige Steuerzeichen**  
  
     Ein Steuerzeichen in der **ACCELERATORS** -Anweisung ist ungültig. Gültige Steuerzeichen besteht aus einem Buchstaben (nur) folgt ein Caretzeichen (^).  
  
31. **Ungültige-Steuerelementtyp**  
  
     Jedes Steuerelement-Anweisung in eine **Dialogfeld** -Anweisung muss eine der folgenden sein: das Kontrollkästchen, COMBOBOX, CONTROL, CTEXT, DEFPUSHBUTTON, EDITTEXT-, GROUPBOX, Symbol, LISTBOX, LTEXT, PUSHBUTTONS, "RadioButton", RTEXT, BILDLAUFLEISTE. Stellen Sie sicher, dass diese Steueranweisungen richtig geschrieben sind.  
  
32. **Ungültiger Typ**  
  
     Der Ressourcentyp war nicht zwischen den Typen in der Datei WINDOWS.h definiert.  
  
33. **Textzeichenfolge oder Ordnungszahl im Steuerelement erwartet**  
  
     Die *Text* Feld eine **Steuerelement** -Anweisung in der **Dialogfeld** -Anweisung muss entweder eine Textzeichenfolge oder den Ordnungszahlverweis in den Typ des Steuerelements sein. Wenn Sie eine Ordnungszahl verwenden, achten Sie darauf, eine `#define` -Anweisung für das Steuerelement zu verwenden.  
  
34. **Nicht übereinstimmende Klammern**  
  
     Stellen Sie sicher, dass Sie alle offenen Klammern geschlossen haben, der **Dialogfeld** Anweisung.  
  
35. **Unerwarteter Wert in RCData**  
  
     Die *raw-data* -Werte in der **RCDATA** -Anweisung müssen ganze Zahlen oder Zeichenfolgen und jeweils durch ein Komma voneinander getrennt sein. Stellen Sie sicher, dass Sie kein Komma oder Anführungszeichen um eine Zeichenfolge vergessen haben.  
  
36. **Unbekannte Menü Untertyp**  
  
     Die *Elementdefinition* Feld der **Menü** Anweisung darf nur **"MenuItem"** und **POPUP** Anweisungen.
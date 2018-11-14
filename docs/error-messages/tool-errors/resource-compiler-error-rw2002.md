---
title: 'Ressourcencompiler: Fehler RW2002'
ms.date: 11/04/2016
f1_keywords:
- RW2002
helpviewer_keywords:
- RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
ms.openlocfilehash: 4cd922fff691b524ec9d278ac5948992fc096e09
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523499"
---
# <a name="resource-compiler-error-rw2002"></a>Ressourcencompiler: Fehler RW2002

Fehler beim Analysieren

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. **Accelerator-Typ erforderlich ist (ASCII oder VIRTKEY)**

   Das `type` -Feld der **ACCELERATORS** -Anweisung muss entweder den ASCII- oder den VIRTKEY-Wert enthalten.

1. **BEGIN in Zugriffstastentabelle erwartet**

   Das **BEGIN** -Schlüsselwort muss direkt auf das **ACCELERATORS** -Schlüsselwort folgen.

1. **BEGIN erwartet im Dialogfeld "**

   Die **beginnen** -Schlüsselwort muss direkt folgen der **Dialogfeld** Schlüsselwort.

1. **BEGIN in Menü erwartet.**

   Das **BEGIN** -Schlüsselwort muss direkt auf das **MENU** -Schlüsselwort folgen.

1. **BEGIN in RCData erwartet.**

   Das **BEGIN** -Schlüsselwort muss direkt auf das **RCDATA** -Schlüsselwort folgen.

1. **BEGIN-Schlüsselwort in Zeichenfolgentabelle erwartet**

   Die **beginnen** -Schlüsselwort muss direkt folgen der **STRINGTABLE** Schlüsselwort.

1. **Zeichenfolgenkonstanten können nicht erneut verwendet werden.**

   Sie verwenden den gleichen Wert, der zweimal in einem **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimale und hexadezimale Werten. Jede ID in einem **STRINGTABLE** muss eindeutig sein. Verwenden Sie für maximale Effizienz bei aufeinander folgende Konstanten, die auf ein Vielfaches von 16 zu starten.

1. **Steuerzeichen außerhalb des gültigen Bereichs [^ A - ^ Z]**

   Ein Steuerzeichen in der **ACCELERATORS** -Anweisung ist ungültig. Das auf das Caretzeichen (**^**) folgende Zeichen muss zwischen A und Z (einschl.) liegen.

1. **Leere Menüs nicht zulässig**

   Ein **END** Schlüsselwort angezeigt wird, bevor alle Menüelemente, in definiert werden der **Menü** Anweisung. Der Ressourcencompiler lässt sich nicht auf leere Menüs aus. Stellen Sie sicher, Sie verfügen nicht über keine öffnenden Anführungszeichen innerhalb der **Menü** Anweisung.

1. **END erwartet im Dialogfeld "**

   Die **END** Schlüsselwort muss erfolgen, am Ende einer **Dialogfeld** Anweisung. Stellen Sie sicher, dass es sind keine geöffneten Angebote, die aus der vorherigen Anweisung übrig.

1. **END in Menü erwartet.**

   Das **END** -Schlüsselwort muss am Ende einer **MENU** -Anweisung stehen. Stellen Sie sicher, dass keine öffnenden Anführungszeichen oder nicht übereinstimmende Paare von **BEGIN** - und **END** -Anweisungen vorhanden sind.

1. **Komma in Zugriffstastentabelle erwartet**

   Der Ressourcencompiler erfordert ein Komma zwischen dem Feld `event` und dem Feld *idvalue* in der **ACCELERATORS** -Anweisung.

1. **erwartete steuerelementklassenname**

   Die `class` Feld eine **Steuerelement** -Anweisung in der **Dialogfeld** -Anweisung muss eine der folgenden Typen sein: Schaltfläche, KOMBINATIONSFELD, bearbeiten, LISTBOX, BILDLAUFLEISTE, statischen und oder eine benutzerdefinierte. Stellen Sie sicher, dass die Klasse richtig geschrieben ist.

1. **Name einer Schriftart erwartet**

   Das Feld *typeface* der FONT-Option in der **DIALOG** -Anweisung muss eine ASCII-Zeichenfolge in doppelten Anführungszeichen sein. Dieses Feld gibt den Namen einer Schriftart an.

1. **Erwarteter ID-Wert für "MenuItem"**

   Die **MENU** -Anweisung muss ein *menuID* -Feld aufweisen, in dem der Name oder die Nummer angegeben ist, der bzw. die die Menüressource identifiziert.

1. **Menüzeichenfolge erwartet**

   Jede **MENUITEM** - und **POPUP** -Anweisung muss ein *Text* -Feld enthalten. Hierbei handelt es sich um eine Zeichenfolge in doppelten Anführungszeichen, die den Namen des Menüelements oder Popupmenüs angibt. Ein **"MenuItem" TRENNZEICHEN** -Anweisung erfordert keine Zeichenfolge in Anführungszeichen.

1. **numerische Befehls-Wert erwartet**

   Der Ressourcencompiler erwartet wurde ein numerisches *Idvalue* -Feld in der **ACCELERATORS** Anweisung. Stellen Sie sicher, dass Sie verwendet haben, eine `#define` Konstante zum Angeben des Werts und dass die Konstante richtig geschrieben ist.

1. **Numerische Konstante erwartet in Zeichenfolgentabelle**

   Eine in einer `#define` -Anweisung definierte numerische Konstante muss direkt auf das **BEGIN** -Schlüsselwort in einer **STRINGTABLE** -Anweisung folgen.

1. **Numerische Punktgröße erwartet**

   Das Feld *pointsize* der Option FONT in der Anweisung **DIALOG** muss ein ganzzahliger Punktgrößenwert sein.

1. **erwartete numerische Dialog-Konstante**

   Ein **Dialogfeld** -Anweisung erfordert ganzzahlige Werte für die *X, y, Breite*, und *Höhe* Felder. Stellen Sie sicher, dass diese Werte nach enthalten sind die **Dialogfeld** -Schlüsselwort und, dass sie nicht negativ sind.

1. **Erwartete Zeichenfolge in STRINGTABLE**

   Nach jedem *stringid* -Wert in einer **STRINGTABLE** -Anweisung wird eine Zeichenfolge erwartet.

1. **Erwartete Zeichenfolge oder Konstantenzugriffstaste**

   Der Ressourcencompiler konnte nicht bestimmen, welche Art von Schlüssel für die Zugriffstaste eingerichtet wurde. Das `event` -Feld in der **ACCELERATORS** -Anweisung ist möglicherweise ungültig.

1. **Zahl erwartet als ID**

   Erwartet eine Zahl für die `id` einer Steuerelement-Anweisung in der **Dialogfeld** Anweisung. Stellen Sie sicher, dass eine Zahl oder `#define` -Anweisung für die Steuerelement-ID.

1. **Zeichenfolge in Anführungszeichen erwartet in Dialogklasse**

   Das `class` -Feld der CLASS-Option in der **DIALOG** -Anweisung muss eine ganze Zahl oder eine Zeichenfolge, die in doppelte Anführungszeichen eingeschlossen ist, enthalten.

1. **Zeichenfolge in Anführungszeichen erwartet in Dialogfeldtitel**

   Das `captiontext` -Feld der CAPTION-Option in der **DIALOG** -Anweisung muss eine ASCII-Zeichenfolge in doppelten Anführungszeichen sein.

1. **Datei wurde nicht gefunden: Dateiname**

   Die in der Befehlszeile des Ressourcencompilers angegebene Datei wurde nicht gefunden. Überprüfen Sie, ob die Datei in ein anderes Verzeichnis verschoben wurde und ob der Dateiname und der Pfad korrekt eingegeben wurden. Für die Verwendung von durchsucht die **INCLUDE** -Umgebungsvariablen oder der Visual Workbench-Einstellung, falls verfügbar.

1. **Schriftartnamen müssen Ordnungszahlen sein.**

   Die *Pointsize* Feld in die Schriftart-Anweisung muss eine ganze Zahl, nicht um eine Zeichenfolge sein.

1. **Ungültige Zugriffstaste**

   Ein `event` -Feld in der **ACCELERATORS** -Anweisung wurde nicht erkannt oder ist mehr als zwei Zeichen lang.

1. **Ungültiger Zugriffstastentyp (ASCII oder VIRTKEY)**

   Das `type` -Feld der **ACCELERATORS** -Anweisung muss entweder den ASCII- oder den VIRTKEY-Wert enthalten.

1. **ungültige Steuerzeichen**

   Ein Steuerzeichen in der **ACCELERATORS** -Anweisung ist ungültig. Ein gültiges Steuerzeichen besteht aus einem Buchstaben (nur) folgt ein Caretzeichen (^).

1. **Ungültiger-Steuerelementtyp**

   Jede Control-Anweisung in einem **Dialogfeld** -Anweisung muss eine der folgenden sein: Kontrollkästchen, COMBOBOX, -Steuerelement, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, Symbol, LISTBOX, LTEXT, PUSHBUTTON, RADIOBUTTON, RTEXT, BILDLAUFLEISTE. Stellen Sie sicher, dass diese Steueranweisungen richtig geschrieben sind.

1. **Ungültiger Typ**

   Der Ressourcentyp war nicht zu den Typen, die in der Datei WINDOWS.h definiert.

1. **Textzeichenfolge oder Ordnungszahl im Steuerelement erwartet**

   Die *Text* Feld eine **Steuerelement** -Anweisung in der **Dialogfeld** -Anweisung muss entweder eine Textzeichenfolge oder einen Ordnungszahlverweis auf den Typ des Steuerelements sein. Wenn Sie eine Ordnungszahl verwenden, achten Sie darauf, eine `#define` -Anweisung für das Steuerelement zu verwenden.

1. **Nicht übereinstimmende Klammern**

   Stellen Sie sicher, dass Sie alle offenen Klammern geschlossen haben, der **Dialogfeld** Anweisung.

1. **Unerwarteter Wert in RCData**

   Die *raw-data* -Werte in der **RCDATA** -Anweisung müssen ganze Zahlen oder Zeichenfolgen und jeweils durch ein Komma voneinander getrennt sein. Stellen Sie sicher, dass Sie kein Komma oder Anführungszeichen um eine Zeichenfolge vergessen haben.

1. **Menü "Unbekannt" Untertyp**

   Die *Elementdefinition* Feld der **Menü** -Anweisung enthalten nur **"MenuItem"** und **POPUP** Anweisungen.
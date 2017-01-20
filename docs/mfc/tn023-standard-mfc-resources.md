---
title: "TN023: MFC-Standardressourcen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.resources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressourcen [MFC]"
  - "Standardressourcen"
  - "TN023"
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# TN023: MFC-Standardressourcen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die Standardressourcen, die mit bereitgestellten und die MFC\-Bibliothek erforderlich sind.  
  
## Standardressourcen  
 MFC bietet zwei vordefinierte Kategorien Ressourcen an, die Sie in Ihrer Anwendung verwenden können: ClipArt\-Ressourcen und Standardframeworkressourcen.  
  
 ClipArt\-Ressourcen sind zusätzliche Ressourcen, dass das Framework nicht davon abhängt, das Sie der Benutzeroberfläche der Anwendung möglicherweise hinzufügen möchten.  Die folgenden ClipArt\-Ressourcen werden generell Beispiel [CLIPART](../top/visual-cpp-samples.md) MFC enthalten:  
  
-   Common.rc: Eine einzelne Datei von Ressourcen, die enthält:  
  
    -   Eine große Auflistung Symbole, die eine Vielzahl des Unternehmens und der Datenverarbeitungscodes Aufgaben.  
  
    -   Einige allgemeine Cursor \(siehe auch Afxres.rc\).  
  
    -   Eine Symbolleistenbitmap, die einige Symbolleisten\-Schaltflächen enthält.  
  
    -   Die Bitmap\- und Symbolressourcen, die von Commdlg.dll verwendet werden.  
  
-   Indicate.rc: Enthält Zeichenfolgenressourcen für die Statusleistentastenzustandsindikatoren, wie "GROSSBUCHSTABEN" für FESTSTELLTASTE.  
  
-   Prompts.rc: Enthält MenüEingabeaufforderungszeichenfolgenressourcen für jeden vordefinierten Befehl, z "erstellen ein neues Dokument" für `ID_FILE_NEW`.  
  
-   Commdlg.rc: Kompatible RC\-Datei Visual C\+\+\-Zielversion, die die standardmäßigen COMMDLG Dialogfeldvorlagen enthält.  
  
 Standardframeworkressourcen sind Ressourcen mit AFX\-definierten IDs, dass das Framework an für interne Implementierungen abhängt.  Sie müssen selten die AFX\-definierten Ressourcen ändern.  Wenn Sie dies tun, sollten Sie der Prozedur So, die weiter unten in diesem Thema beschrieben wird.  
  
 Die folgenden Frameworkressourcen sind im Verzeichnis MFC\\INCLUDE enthalten:  
  
-   Afxres.rc: Allgemeine Ressourcen verwendet vom Framework.  
  
-   Afxprint.rc: Ressourcen spezifisch auf Druckfunktionen.  
  
-   Afxolecl.rc: Ressourcen spezifisch für OLE\-Clientanwendungen.  
  
-   Afxolev.rc: Ressourcen spezifisch zu vollständigen OLE\-Serveranwendungen.  
  
## Verwenden der ClipArt\-Ressourcen  
  
#### Um eine ClipArt\-Binärdateiressource verwenden  
  
1.  Öffnen Sie die Ressourcendatei der Anwendung in Visual C\+\+.  
  
2.  Öffnen Sie Common.rc.  Diese Datei enthält alle ClipArt\-Ressourcen binären.  Dies nimmt ggf. etwas Zeit, da die Common.rc\-Datei kompiliert wird.  
  
3.  Halten Sie STRG gedrückt während die Ressourcen ziehen, die Sie von Common.rc auf die Ressourcendatei der Anwendung verwenden möchten.  
  
 Um andere ClipArt\-Ressourcen verwenden, befolgen Sie die gleichen Schritte aus.  Der einzige Unterschied ist, dass Sie die passende RC\-Datei anstelle Common.rc öffnen.  
  
> [!NOTE]
>  Achten Sie darauf, dass Sie nicht unbeabsichtigterweise Ressourcen aus Common.rc out dauerhaft verschieben.  Wenn Sie die STRG\-TASTE gedrückt halten, während Sie Ressourcen ziehen, erstellen Sie eine Kopie.  Wenn Sie die STRG\-TASTE nicht gedrückt halten, während Sie ziehen, werden die Ressourcen verschoben.  Wenn Sie besorgt sind, dass Sie möglicherweise versehentlich Änderungen an der Common.rc\-Datei vorgenommen, klicken Sie "Keine" wenn Sie gefragt werden, ob die Änderungen an Common.rc speichert.  
  
> [!NOTE]
>  Die .rc\-Ressourcendateien weisen eine besondere `TEXTINCLUDE` Ressource in ihnen, die an Sie versehentlich speichern auf die Standardrc\-dateien verhindern.  
  
### Anpassen von Standardframework\-Ressourcen  
 Standardframeworkressourcen werden normalerweise in einer Anwendung enthalten, indem der \#include Befehl in der Ressourcendatei einer Anwendung.  Anwendungs\-Assistent generiert eine Ressourcendatei.  Diese Datei enthält die Frameworkressourcen des geeigneten Standardwert, abhängig von den Optionen des Anwendungs\-Assistenten Sie auswählen.  Sie können überprüfen, hinzufügen oder entfernen, welche Ressourcen enthalten sind, indem die Kompilierzeitdirektive ändert.  Hierzu, öffnen Sie das Menü **Ressource** und wählen Sie **Includes festlegen** aus.  Betrachten Sie das "Kompilierzeitdirektiven" Bearbeitungselement.  Beispiel:  
  
```  
#include "afxres.rc"  
#include "afxprint.rc"  
```  
  
 Der häufigste Fall dem Anpassen von Standardframeworkressourcen ist, hinzugefügt oder entfernt zusätzlichen Include für das Drucken, OLE\-Client und OLE\-Server Unterstützung.  
  
 In einigen wenigen Fällen sollten Sie den Inhalt der Standardframeworkressourcen für Ihre spezielle Anwendung anpassen, die gesamte Datei gegenwärtig nicht hinzuzufügen und zu entfernen.  Die Followingsschritte zeigen, wie Sie die Ressourcen einschränken können, die enthalten sind:  
  
##### Um den Inhalt einer Standardressourcendatei anpassen  
  
1.  Öffnen Sie die Ressourcendatei in Visual C\+\+.  
  
2.  Verwenden der Ressourcen\-Satz\-Einschließung Sie einen EXE\-Befehl, entfernen Sie `#include` für die Standardrc\-datei, die Sie anpassen möchten.  Um beispielsweise die Seitenansichtssymbolleiste anzupassen, entfernen Sie die Zeile `#include "afxprint.rc"`.  
  
3.  Öffnen Sie die entsprechenden Standardressourcendateien in MFC\\INCLUDE.  Nach dem Beispiel weiter oben in diesem Thema lautet die entsprechende Datei MFC\\Include\\Aafxprint.rc  
  
4.  Kopieren Sie alle Ressourcen aus der Standardrc\-datei zu der Anwendungsressourcendatei.  
  
5.  Ändern Sie die Kopie der Standardressourcen in der Anwendungsressourcendatei.  
  
> [!NOTE]
>  Ändern Sie keinesfalls die Ressourcen direkt in den Standardrc\-dateien.  Somit transitive ändert die Ressourcen, die in jeder Anwendung, nicht nur in der verfügbar sind, die Sie gerade arbeiten.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
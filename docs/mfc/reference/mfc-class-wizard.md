---
title: "MFC-Klassen-Assistent"
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
  - "vc.wizards.classwizard"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Klassen-Assistent"
  - "Assistenten (MFC)"
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-Klassen-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht das Hinzufügen von Meldungen und Meldungshandlern zu Klassen im Projekt.  Sie können auch andere Assistenten starten oder dem Projekt eine Klasse hinzufügen.  
  
 Klicken Sie zum Öffnen des **MFC\-Klassen\-Assistenten** im Menü **Projekt** auf **Klassen\-Assistent**.  Drücken Sie zum Öffnen des Assistenten mit einer Tastenkombination STRG\+UMSCHALT\+X.  
  
## UIElement-Liste  
 **Projekt**  
 Der Name eines Projekts in der Lösung.  
  
 Sie können andere Projekte in der Projektmappe im Dropdown\-Listenfeld auswählen.  
  
 **Klassenname**  
 Der Name einer Klasse im Projekt.  
  
 Wenn Sie in der Liste **Klassenname** eine Klasse auswählen, füllen Daten aus der Klasse die Steuerelemente im **MFC\-Klassen\-Assistenten** auf.  Wenn Sie den Wert eines Steuerelements ändern, sind Daten in der ausgewählten Klasse betroffen.  
  
 **Klasse hinzufügen**  
 Ermöglicht das Hinzufügen einer Klasse aus einer von mehreren Quellen.  
  
 Abhängig von der Auswahl wird der **MFC\-Assistent zum Hinzufügen von Klassen**, der **Assistent zum Hinzufügen von Klassen aus der Typbibliothek**, der **Assistent zum Hinzufügen von Klassen aus ActiveX\-Steuerelementen** oder der **MFC\-ODBC\-Consumer\-Assistent** gestartet.  
  
 **Basisklasse**  
 Die Basisklasse der Klasse, die in **Klassenname** angezeigt wird.  
  
 **Klassendeklaration**  
 Die Klasse, in der die **Klassenname**\-Klasse deklariert ist.  
  
 Das Feld **Klassendeklaration** wird nur angezeigt, wenn sich der Name darin vom Namen in **Klassenimplementierung** unterscheidet.  
  
 **Ressource**  
 Gegebenenfalls die ID der Ressource in **Klassenname**.  Andernfalls ist das Feld **Ressource** leer.  
  
 **Klassenimplementierung**  
 Der Name der Datei, die die Implementierung der Klasse in **Klassenname** enthält.  
  
 Sie können eine andere Implementierungsdatei auswählen, indem Sie auf den Pfeil klicken.  In der folgenden Tabelle sind die verfügbaren Optionen aufgelistet.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Datei öffnen**|Beendet den Klassen\-Assistenten und öffnet die aktuelle Klassenimplementierungsdatei.|  
|**Enthaltenden Ordner öffnen**|Öffnet den Ordner, der die aktuelle Klassenimplementierungsdatei enthält.|  
|**Vollständigen Pfad in die Zwischenablage kopieren**|Kopiert den Pfad der aktuellen Implementierungsdatei in die Zwischenablage.|  
  
 **Befehle**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einem Befehl und seinem Meldungshandler.  
  
 Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder doppelklicken Sie in der Liste **Objekt\-IDs** oder **Meldungen** auf ein Element.  Der resultierende Funktionsname, die ID und die Meldung werden in der Liste **Memberfunktionen** angezeigt.  
  
 Um einen Handler zu löschen, wählen Sie in der Liste **Memberfunktionen** ein Element aus, und klicken Sie dann auf **Handler löschen**.  
  
 Um einen Handler zu ändern, doppelklicken Sie in der Liste **Memberfunktionen** auf das entsprechende Element.  Oder wählen Sie ein Element im Listenfeld aus, und klicken Sie dann auf **Code bearbeiten**.  
  
 **Meldungen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Meldung und ihrem Meldungshandler.  
  
 Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder doppelklicken Sie in der Liste **Meldungen** auf ein Element.  
  
 Um eine benutzerdefinierte Meldung hinzuzufügen, klicken Sie auf **Benutzerdefinierte Meldung hinzufügen** oder drücken die EINGABETASTE, und geben Sie dann Werte im Dialogfeld **Benutzerdefinierte Meldung hinzufügen** an.  In diesem Dialogfeld können Sie auch **Registrierte Meldung** auswählen, um eine Fenstermeldung zu behandeln, die im Betriebssystem garantiert eindeutig ist.  
  
 **Virtuelle Funktionen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer virtuellen Funktion oder einer überschriebenen virtuellen Funktion.  
  
 **Membervariablen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Membervariable.  
  
 **Methoden**  
 Ermöglicht das Hinzufügen, Löschen oder Suchen nach einer Methode. Sie können auch zur Definition oder der Deklaration einer Methode wechseln.  
  
 Um eine benutzerdefinierte Methode hinzuzufügen, klicken Sie auf **Methode hinzufügen**, und geben Sie dann Werte im Dialogfeld **Methode hinzufügen** an.  
  
 Um eine Methode zu löschen, wählen Sie in der Liste **Methoden** ein Element aus, und klicken Sie dann auf **Methode löschen**.  
  
 Um eine Deklaration anzuzeigen, wählen Sie in der Liste **Methoden** ein Element aus, und klicken Sie dann auf **Gehe zu Deklaration**.  
  
 Um eine Definition anzuzeigen, doppelklicken Sie in der Liste **Methoden** auf ein Element.  Oder wählen Sie ein Element in der Liste **Methoden** aus, und klicken Sie dann auf die Schaltfläche **Gehe zu Definition**.  
  
## Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
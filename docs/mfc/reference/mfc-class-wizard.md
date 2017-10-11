---
title: MFC-Klassen-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.wizards.classwizard
dev_langs:
- C++
helpviewer_keywords:
- wizards (MFC)
- MFC Class Wizard
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 2d8a0e18da58829175a973bf31b2597240e23bd8
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="mfc-class-wizard"></a>MFC-Klassen-Assistent
Ermöglicht das Hinzufügen von Meldungen und Meldungshandlern zu Klassen im Projekt. Sie können auch andere Assistenten starten oder dem Projekt eine Klasse hinzufügen.  
  
 So öffnen die **MFC-Klassen-Assistent**auf die **Projekt** Menü klicken Sie auf **Klassen-Assistent**. Drücken Sie zum Öffnen des Assistenten mit einer Tastenkombination STRG+UMSCHALT+X.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Projekt**  
 Der Name eines Projekts in der Lösung.  
  
 Sie können andere Projekte in der Projektmappe im Dropdown-Listenfeld auswählen.  
  
 **Klassenname**  
 Der Name einer Klasse im Projekt.  
  
 Bei Auswahl eine Klasse in der **Klassenname** Liste, die Daten aus der Klasse füllt die Steuerelemente in der **MFC-Klassen-Assistent**. Wenn Sie den Wert eines Steuerelements ändern, sind Daten in der ausgewählten Klasse betroffen.  
  
 **Klasse hinzufügen**  
 Ermöglicht das Hinzufügen einer Klasse aus einer von mehreren Quellen.  
  
 Abhängig von Ihrer Auswahl der **MFC-Assistenten zum Hinzufügen von Klassen**, **Assistenten zum Hinzufügen von Klassen aus der Typbibliothek**, **Assistenten zum Hinzufügen von Klassen aus ActiveX-Steuerelement**, oder **MFC-ODBC Consumer-Assistent** gestartet wird.  
  
 **Basisklasse**  
 Die Basisklasse der Klasse, die in angezeigt wird **Klassenname**.  
  
 **Klassendeklaration**  
 Die Klasse, in der die **Klassenname** Klasse deklariert wird.  
  
 Die **-Klassendeklaration** Feld wird nur angezeigt, wenn der Name darin vom Namen in unterscheidet sich **klassenimplementierung**.  
  
 **Ressource**  
 Die ID der Ressource **Klassenname**, sofern vorhanden. Andernfalls die **Ressource** Feld leer ist.  
  
 **Klassenimplementierung**  
 Der Name der Datei, die die Implementierung der Klasse in enthält **Klassenname**.  
  
 Sie können eine andere Implementierungsdatei auswählen, indem Sie auf den Pfeil klicken. In der folgenden Tabelle sind die verfügbaren Optionen aufgelistet.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Datei öffnen**|Beendet den Klassen-Assistenten und öffnet die aktuelle Klassenimplementierungsdatei.|  
|**Öffnen Sie enthaltenden Ordner**|Öffnet den Ordner, der die aktuelle Klassenimplementierungsdatei enthält.|  
|**Vollständigen Pfad in die Zwischenablage kopieren**|Kopiert den Pfad der aktuellen Implementierungsdatei in die Zwischenablage.|  
  
 **Befehle**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einem Befehl und seinem Meldungshandler.  
  
 Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder doppelklicken Sie auf ein Element in der **Objekt-IDs** Liste oder **Nachrichten** Liste. Der resultierende Funktionsname, ID und Meldung werden angezeigt, der **Memberfunktionen** Liste.  
  
 Um einen Handler zu löschen, wählen Sie ein Element in der **Memberfunktionen** aus, und klicken Sie dann auf **Handler löschen**.  
  
 Um einen Handler zu ändern, doppelklicken Sie auf das entsprechende Element in der **Memberfunktionen** Liste. Oder wählen Sie ein Element im Listenfeld, und klicken Sie dann auf **-Code bearbeiten**.  
  
 **Meldungen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Meldung und ihrem Meldungshandler.  
  
 Um einen Handler hinzuzufügen, klicken Sie auf **Handler hinzufügen**, oder doppelklicken Sie auf ein Element in der **Nachrichten** Liste.  
  
 Um eine benutzerdefinierte Meldung hinzuzufügen, klicken Sie auf **benutzerdefinierte Meldung hinzufügen** oder drücken Sie die EINGABETASTE, und geben Sie Werte in der **benutzerdefinierte Meldung hinzufügen** (Dialogfeld). Sie können auch auswählen, in diesem Dialogfeld **registrierte Meldung** eine fenstermeldung zu behandeln, die garantiert im gesamten Betriebssystem eindeutig sein.  
  
 **Virtuelle Funktionen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer virtuellen Funktion oder einer überschriebenen virtuellen Funktion.  
  
 **Membervariablen**  
 Ermöglicht das Hinzufügen, Löschen, Bearbeiten oder Suchen nach einer Membervariable.  
  
 **Methoden**  
 Ermöglicht das Hinzufügen, Löschen oder Suchen nach einer Methode. Sie können auch zur Definition oder der Deklaration einer Methode wechseln.  
  
 Um eine Methode hinzuzufügen, klicken Sie auf **Methode hinzufügen**, und geben Sie Werte in der **Methode hinzufügen** (Dialogfeld).  
  
 Um eine Methode zu löschen, wählen Sie ein Element in der **Methoden** aus, und klicken Sie dann auf **Methode Delete**.  
  
 Um eine Deklaration anzuzeigen, wählen Sie ein Element in der **Methoden** aus, und klicken Sie dann auf **Gehe zu Deklaration.**  
  
 Um eine Definition anzuzeigen, doppelklicken Sie auf ein Element in der **Methoden** Liste. Oder wählen Sie ein Element in der **Methoden** aus, und klicken Sie dann auf die **Gehe zu Definition** Schaltfläche.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)


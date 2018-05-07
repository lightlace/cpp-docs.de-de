---
title: Überschreiben einer virtuellen Funktion (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-a-virtual-function-visual-c"></a>Überschreiben einer virtuellen Funktion (Visual C++)
Sie können angeben, überschreiben virtuelle Funktionen in einer Basisklasse von Visual Studio [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Eine virtuelle Funktion im Fenster Eigenschaften überschreiben  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **überschreibt** Schaltfläche.  
  
    > [!NOTE]
    >  Die **überschreibt** Schaltfläche ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht oder im Quellcodefenster auf auswählen.  
  
     Die linke Spalte listet die virtuellen Funktionen. Wenn der Name einer virtuellen Funktion auch in der rechten Spalte angezeigt wird, wurde bereits eine Überschreibung implementiert.  
  
3.  Wenn die Funktion keine Überschreibung, klicken Sie dann auf die Zelle in der rechten Spalte im Fenster "Eigenschaften" den empfohlenen Name der Funktion angezeigt auf Überschreiben als \<hinzufügen >*FuncName*.  
  
4.  Klicken Sie auf den vorgeschlagenen Namen Stubcode für die Funktion hinzufügen.  
  
5.  Um eine überschreibende Funktion bearbeiten möchten, doppelklicken Sie auf den Namen der Funktion in der Klassenansicht und bearbeiten Sie den Code im Quellcodefenster.  
  
 Um eine Überschreibung zu entfernen, klicken Sie auf die Außerkraftsetzung Funktionsnamen in der rechten Spalte aus, und wählen Sie \<Löschen >*FuncName*. Der Code der Funktion wird auskommentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)
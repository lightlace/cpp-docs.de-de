---
title: Überschreiben einer virtuellen Funktion (Visual C++) | Microsoft-Dokumentation
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337742"
---
# <a name="overriding-a-virtual-function-visual-c"></a>Überschreiben einer virtuellen Funktion (Visual C++)
Sie können virtuelle Funktionen überschreiben, die in einer Basisklasse des [Eigenschaftenfensters](/visualstudio/ide/reference/properties-window) von Visual Studio definiert sind.  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>So überschreiben Sie eine virtuelle Funktion im Eigenschaftenfenster  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Überschreibungen**.  
  
    > [!NOTE]
    >  Die Schaltfläche **Überschreibungen** ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht auswählen oder in das Quellcodefenster klicken.  
  
     In der linken Spalte werden die virtuellen Funktionen aufgelistet. Wenn der Name einer virtuellen Funktion auch in der rechten Spalte angezeigt wird, wurde bereits eine Überschreibung implementiert.  
  
3.  Wenn die Funktion über keine Überschreibung verfügt, klicken Sie auf die Zelle in der rechten Spalte des Eigenschaftenfensters, um den empfohlenen Namen der Funktionsüberschreibung als \<add>*FuncName* anzuzeigen.  
  
4.  Klicken Sie auf den empfohlenen Namen, um Stubcode für die Funktion hinzuzufügen.  
  
5.  Führen Sie zum Bearbeiten einer überschreibenden Funktion einen Doppelklick auf den Namen der Funktion in der Klassenansicht aus, und bearbeiten Sie den Code im Quellcodefenster.  
  
 Klicken Sie zum Entfernen einer Überschreibung auf den Namen der Überschreibungsfunktion in der rechten Spalte, und klicken Sie auf \<delete>*FuncName*. Der Code der Funktion wird auskommentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding a Class (Hinzufügen einer Klasse)](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigating the Class Structure (Navigieren in der Klassenstruktur)](../ide/navigating-the-class-structure-visual-cpp.md)
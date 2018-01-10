---
title: Suchen von Zeichenfolgen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.string
dev_langs: C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a66b5dd34aa21a2a0791ecbc71bfd4abcc90c4fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="finding-a-string"></a>Suchen von Zeichenfolgen
Sie können eine oder mehrere Zeichenfolgen in der Zeichenfolgentabelle suchen und [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) mit der **in Dateien suchen** Befehl (**bearbeiten** im Menü), suchen Sie alle Instanzen von Zeichenfolgen die einem Muster entsprechen.  
  
### <a name="to-find-a-string-in-the-string-table"></a>Um eine Zeichenfolge in der Zeichenfolgentabelle zu suchen  
  
1.  Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Auf der **bearbeiten** Menü klicken Sie auf **suchen und Ersetzen**, wählen Sie dann **suchen**.  
  
3.  In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Beschriftung Text bzw. Ressourcenidentifizierer Bezeichner der Zeichenfolge, die Sie suchen möchten.  
  
4.  Aktivieren Sie keines der **suchen** Optionen.  
  
5.  Klicken Sie auf **Weitersuchen**.  
  
    > [!TIP]
    >  Um reguläre Ausdrücke werden beim Durchsuchen von Dateien verwenden, verwenden die **in Dateien suchen** Befehl. Geben Sie einen regulären Ausdruck einem Muster entsprechen, oder klicken Sie auf die Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im die **Suchen nach** Feld. Wenn Sie reguläre Ausdrücke verwenden, müssen Sie die **verwenden: reguläre Ausdrücke** Kontrollkästchen aktiviert ist.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen-Editor](../windows/string-editor.md)   


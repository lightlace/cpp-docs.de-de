---
title: Verschieben eine Zeichenfolge aus einer Ressourcendatei in eine andere | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ecb999052aa23d173a6a4113007cbd8452510e5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Verschieben von Zeichenfolgen zwischen Ressourcendateien
### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Eine Zeichenfolge aus einer Ressourcenskriptdatei auf einen anderen verschoben.  
  
1.  Öffnen Sie die Zeichenfolgentabellen in beide RC-Dateien. (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Mit der rechten Maustaste in der Zeichenfolge, die Sie verschieben möchten und wählen **Ausschneiden** aus dem Kontextmenü.  
  
3.  Platzieren Sie den Cursor in das Ziel **Zeichenfolgen-Editor** Fenster.  
  
4.  In der RC-Datei in die Sie verschieben, die Zeichenfolge möchten, mit der Maustaste, und wählen Sie **einfügen** aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Wenn die **ID** oder **Wert** der verschobenen Zeichenfolge Konflikte mit vorhandenen **ID** oder **Wert** in der Zieldatei entweder den **ID** oder **Wert** der verschobenen Zeichenfolge geändert. Eine Zeichenfolge mit dem gleichen ggf. **ID**, die **ID** der verschobenen Zeichenfolge geändert. Eine Zeichenfolge mit dem gleichen ggf. **Wert**, die **Wert** der verschobenen Zeichenfolge geändert.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen-Editor](../windows/string-editor.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Anpassen von Fensterlayouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)   


---
title: Hinzufügen oder Löschen von Zeichenfolgen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables, deleting strings
- strings [C++], deleting in string tables
- string tables, adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e15e29c99dba89ef29ba5b909c62f819bedf63f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858756"
---
# <a name="adding-or-deleting-a-string"></a>Hinzufügen oder Löschen von Zeichenfolgen
Sie können schnell neue Einträge in der Zeichenfolgentabelle im Zeichenfolgen-Editor einfügen. Neue Zeichenfolgen befinden sich am Ende der Tabelle und den nächsten verfügbaren Bezeichner angegeben werden. Bearbeiten Sie Sie dann die Eigenschaften-ID, Wert oder Beschriftung in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) nach Bedarf.  
  
 Die Zeichenfolgen-Editor stellt sicher, dass Sie keine ID verwenden, die bereits verwendet wird. Wenn Sie eine ID bereits verwendet auswählen, wird der Zeichenfolgen-Editor benachrichtigt zu werden und weisen Sie eine generische eindeutige ID, z. B. IDS_STRING58113.  
  
### <a name="to-add-a-string-table-entry"></a>So fügen Sie einer Zeichenfolgentabelle einen Eintrag hinzu  
  
1.  Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Mit der rechten Maustaste in der Zeichenfolgentabelle, und wählen Sie **neue Zeichenfolge** aus dem Kontextmenü.  
  
3.  In der **Zeichenfolge** -Editor, wählen Sie eine **ID** aus der ID-Dropdownliste oder geben eine ID direkt vorhanden.  
  
4.  Bearbeiten der **Wert**, falls erforderlich.  
  
5.  Geben Sie einen Eintrag für die **Beschriftung**.  
  
    > [!NOTE]
    >  NULL-Zeichenfolgen sind in Windows-Zeichenfolgentabellen nicht zulässig. Wenn Sie einen Eintrag in der Zeichenfolgentabelle, die eine null-Zeichenfolge ist erstellen, erhalten Sie eine Nachricht, und Sie werden gefragt, "Bitte geben Sie eine Zeichenfolge für diesen Tabelleneintrag."  
  
### <a name="to-delete-a-string-table-entry"></a>So löschen Sie eine Zeichenfolge-Tabelleneintrag  
  
1.  Wählen Sie den zu löschenden Eintrag aus.  
  
2.  Auf der **bearbeiten** Menü klicken Sie auf **löschen**.  
  
 \- oder –  
  
-   Mit der rechten Maustaste in der Zeichenfolge, die Sie löschen möchten und wählen **löschen** aus dem Kontextmenü.  
  
 \- oder –  
  
-   Drücken Sie die **löschen** Schlüssel.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen-Editor](../windows/string-editor.md)   


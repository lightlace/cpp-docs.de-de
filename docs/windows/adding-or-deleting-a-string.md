---
title: Hinzufügen oder Löschen von Zeichenfolgen | Microsoft-Dokumentation
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
ms.openlocfilehash: 90a470aa5bb1b24ab2fe549f098a83c29e5d0828
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464148"
---
# <a name="adding-or-deleting-a-string"></a>Hinzufügen oder Löschen von Zeichenfolgen
Sie können schnell neue Einträge in der Tabelle mit den Zeichenfolgen-Editor einfügen. Neue Zeichenfolgen befinden sich am Ende der Tabelle und den nächsten verfügbaren Bezeichner erhalten. Sie können dann die Eigenschaften-ID, Wert und Beschriftung im Bearbeiten der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) je nach Bedarf.  
  
 Die Zeichenfolgen-Editor stellt sicher, dass Sie keine ID verwenden, die bereits verwendet wird. Wenn Sie eine ID bereits in Verwendung auswählen, wird der Zeichenfolgen-Editor benachrichtigt Sie, und weisen dann eine generische eindeutige ID, z. B. IDS_STRING58113.  
  
### <a name="to-add-a-string-table-entry"></a>Zum Hinzufügen eines Eintrags der Zeichenfolge-Tabelle  
  
1.  Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Mit der rechten Maustaste in der Tabelle, und wählen Sie **neue Zeichenfolge** aus dem Kontextmenü.  
  
3.  In der **Zeichenfolge** -Editor, wählen eine **ID** aus der ID Dropdown-Liste oder geben Sie eine ID direkt vorhanden.  
  
4.  Bearbeiten der **Wert**, falls erforderlich.  
  
5.  Geben Sie einen Eintrag für die **Beschriftung**.  
  
    > [!NOTE]
    >  NULL-Zeichenfolgen werden in der Windows-Zeichenfolgentabellen nicht zulässig. Wenn Sie einen Eintrag in der Zeichenfolgentabelle, die eine null-Zeichenfolge ist erstellen, erhalten Sie eine Meldung gebeten, "Bitte geben Sie eine Zeichenfolge für diesen Tabelleneintrag."  
  
### <a name="to-delete-a-string-table-entry"></a>So löschen Sie einen Zeichenfolgeneintrag-Tabelle  
  
1.  Wählen Sie den zu löschenden Eintrag aus.  
  
2.  Auf der **bearbeiten** Menü klicken Sie auf **löschen**.  
  
 \- oder –  
  
-   Mit der rechten Maustaste in der Zeichenfolge, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.  
  
 \- oder –  
  
-   Drücken Sie die **löschen** Schlüssel.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Exemplarische Vorgehensweise: Verwenden von Ressourcen für die Lokalisierung mit ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen-Editor](../windows/string-editor.md)   
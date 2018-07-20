---
title: Zeichenfolgen-Editor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string.F1
dev_langs:
- C++
helpviewer_keywords:
- String editor
- string tables
- string tables, String editor
- string editing
- string editing, string tables
- resource editors, String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23211293313135cb0341ac234014ae3c144b7fec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891375"
---
# <a name="string-editor"></a>Zeichenfolgen-Editor
Eine Zeichenfolgentabelle in einer Windows-Ressource, die eine Liste mit IDs, Werten und Beschriftungen für alle Zeichenfolgen Ihrer Anwendung enthält. Beispielsweise befinden sich die Statusleistenmeldungen in der Zeichenfolgentabelle.  
  
 Beim Entwickeln einer Anwendung können Sie mehrere Zeichenfolgentabellen verwenden – eine für jede Sprache oder Bedingung. Ein ausführbares Moduls weist jedoch nur eine Zeichenfolgentabelle auf. Eine ausgeführte Anwendung kann auf verschiedene Zeichenfolgentabellen verweisen, wenn Sie die Tabellen in verschiedenen DLLs platzieren.  
  
 Mithilfe von Zeichenfolgentabellen können Sie Ihre Anwendung bequem in verschiedene Sprachen lokalisieren. Wenn sich alle Zeichenfolgen in einer Zeichenfolgentabelle befinden, können Sie die Anwendung lokalisieren, indem Sie die Zeichenfolgen (und andere Ressourcen) übersetzen, ohne den Quellcode zu ändern. Dies ist normalerweise sinnvoller, als manuell verschiedene Zeichenfolgen in Quelldateien zu suchen und zu ersetzen.  
  
 Mithilfe des Zeichenfolgen-Editors können Sie diese Aktionen ausführen:  
  
-   [Suche nach einer oder mehreren Zeichenfolge(n)](../windows/finding-a-string.md).  
  
-   Schnell [neue Einträge](../windows/adding-or-deleting-a-string.md) in die Zeichenfolgentabelle einfügen.  
  
-   [Eine Zeichenfolge aus einer Ressourcendatei in eine andere verschieben](../windows/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [Direkte Bearbeitung für die Eigenschaften „ID“, „Value“ und „Caption“ verwenden](../windows/changing-the-properties-of-a-string.md) und Änderungen sofort anzeigen.  
  
-   [Die „caption“-Eigenschaft mehrerer Zeichenfolgen ändern](../windows/changing-the-caption-property-of-multiple-strings.md)  
  
-   [Einer Zeichenfolge Formatierungs- oder Sonderzeichen hinzufügen](../windows/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows erlaubt die Erstellung leerer Zeichenfolgentabellen nicht. Wenn Sie eine Zeichenfolgentabelle ohne Einträge erstellen, wird sie beim Speichern der Ressourcendatei automatisch gelöscht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Zeichenfolgen](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Informationen über Zeichenfolgen](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)


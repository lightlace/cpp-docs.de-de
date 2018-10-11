---
title: Zeichenfolgen-Editor (C++) | Microsoft-Dokumentation
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
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9026d016f54bc4aff37be9c6e318837ad1855d1a
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081523"
---
# <a name="string-editor-c"></a>Zeichenfolgen-Editor (C++)

Eine Zeichenfolgentabelle in einer Windows-Ressource, die eine Liste mit IDs, Werten und Beschriftungen für alle Zeichenfolgen Ihrer Anwendung enthält. Beispielsweise befinden sich die Statusleistenmeldungen in der Zeichenfolgentabelle.

Beim Entwickeln einer Anwendung können Sie mehrere Zeichenfolgentabellen verwenden – eine für jede Sprache oder Bedingung. Ein ausführbares Moduls weist jedoch nur eine Zeichenfolgentabelle auf. Eine ausgeführte Anwendung kann auf verschiedene Zeichenfolgentabellen verweisen, wenn Sie die Tabellen in verschiedenen DLLs platzieren.

Mithilfe von Zeichenfolgentabellen können Sie Ihre Anwendung bequem in verschiedene Sprachen lokalisieren. Wenn sich alle Zeichenfolgen in einer Zeichenfolgentabelle befinden, können Sie die Anwendung lokalisieren, indem Sie die Zeichenfolgen (und andere Ressourcen) übersetzen, ohne den Quellcode zu ändern. Dies ist normalerweise sinnvoller, als manuell verschiedene Zeichenfolgen in Quelldateien zu suchen und zu ersetzen.

Mithilfe des Zeichenfolgen-Editors können Sie diese Aktionen ausführen:

- [Suche nach einer oder mehreren Zeichenfolge(n)](../windows/finding-a-string.md).

- Schnell [neue Einträge](../windows/adding-or-deleting-a-string.md) in die Zeichenfolgentabelle einfügen.

- [Eine Zeichenfolge aus einer Ressourcendatei in eine andere verschieben](../windows/moving-a-string-from-one-resource-file-to-another.md)

- [Direkte Bearbeitung für die Eigenschaften „ID“, „Value“ und „Caption“ verwenden](../windows/changing-the-properties-of-a-string.md) und Änderungen sofort anzeigen.

- [Die „caption“-Eigenschaft mehrerer Zeichenfolgen ändern](../windows/changing-the-caption-property-of-multiple-strings.md)

- [Einer Zeichenfolge Formatierungs- oder Sonderzeichen hinzufügen](../windows/adding-formatting-or-special-characters-to-a-string.md)

   > [!NOTE]
   > Windows erlaubt die Erstellung leerer Zeichenfolgentabellen nicht. Wenn Sie eine Zeichenfolgentabelle ohne Einträge erstellen, wird sie beim Speichern der Ressourcendatei automatisch gelöscht.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Zeichenfolgen](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[Informationen über Zeichenfolgen](/windows/desktop/menurc/about-strings)


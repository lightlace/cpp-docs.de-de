---
title: 'Vorgehensweise: Symbolsuche in Ressourcen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0635751fa052c6e6a54d958e9005fee80812f7d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012101"
---
# <a name="how-to-search-for-symbols-in-resources"></a>Gewusst wie: Symbolsuche in Ressourcen
### <a name="to-find-symbols-in-resources"></a>So suchen Sie Symbole in Ressourcen  
  
1.  Von der **bearbeiten** Menü wählen **Suchsymbol**.  
  
2.  In der [Suchsymbol-Dialogfeld](http://msdn.microsoft.com/63e93d9c-784f-418d-a76a-723da5ff5d96)in die **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown Liste aus, oder geben Sie die Zugriffstaste, die Sie (z. B. ID_ACCEL1) suchen möchten.  
  
    > [!TIP]
    >  Mit [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) für die Suche, müssen Sie verwenden die [Befehl in Dateien suchen](/visualstudio/ide/reference/find-command) aus der **bearbeiten** Menü anstelle von der **Suchsymbol**Befehl. Um reguläre Ausdrücke zu aktivieren, müssen Sie die **verwenden: reguläre Ausdrücke** Kontrollkästchen der [suchen (Dialogfeld)](http://msdn.microsoft.com/dad03582-4931-4893-83ba-84b37f5b1600). Anschließend können Sie auf, die nach-rechts Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld.  
  
3.  Aktivieren Sie keines der **finden** Optionen.  
  
4.  Klicken Sie auf **Weitersuchen**.  
  
    > [!NOTE]
    >  Die Suche nach Symbolen in Zeichenfolgen-, Zugriffstasten- oder Binärressourcen wird nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)aus.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)
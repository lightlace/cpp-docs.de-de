---
title: 'Vorgehensweise: Symbolsuche in Ressourcen | Microsoft Docs'
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
ms.openlocfilehash: b45780223191c8dacec12d5312f4d2ac724b4d4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880217"
---
# <a name="how-to-search-for-symbols-in-resources"></a>Gewusst wie: Symbolsuche in Ressourcen
### <a name="to-find-symbols-in-resources"></a>So suchen Sie Symbole in Ressourcen  
  
1.  Aus der **bearbeiten** Menü wählen **Symbol suchen**.  
  
2.  In der [Symbol suchen (Dialogfeld)](http://msdn.microsoft.com/en-us/63e93d9c-784f-418d-a76a-723da5ff5d96)in der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Zugriffstaste ein (z. B. ID_ACCEL1) werden sollen.  
  
    > [!TIP]
    >  Verwenden [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) verwenden Sie für die Suche der [Befehl in Dateien suchen](/visualstudio/ide/reference/find-command) aus der **bearbeiten** Menü statt der **Symbol suchen**Befehl. Um reguläre Ausdrücke zu aktivieren, benötigen Sie die **verwenden: reguläre Ausdrücke** Kontrollkästchen der [suchen (Dialogfeld)](http://msdn.microsoft.com/en-us/dad03582-4931-4893-83ba-84b37f5b1600). Dann Sie auf den nach rechts weisenden Pfeil rechts neben klicken der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im die **Suchen nach** Feld.  
  
3.  Aktivieren Sie keines der **suchen** Optionen.  
  
4.  Klicken Sie auf **Weitersuchen**.  
  
    > [!NOTE]
    >  Die Suche nach Symbolen in Zeichenfolgen-, Zugriffstasten- oder Binärressourcen wird nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)aus.  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)
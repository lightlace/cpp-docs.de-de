---
title: 'Vorgehensweise: Symbolsuche in Ressourcen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 154c7a7284272ceef7a3e2d82fcd90d05069b7fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
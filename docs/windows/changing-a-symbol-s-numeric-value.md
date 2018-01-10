---
title: "Ändern eines Symbols &#39; s numerischen Wert | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.changing.value
dev_langs: C++
helpviewer_keywords:
- numeric values
- symbols, numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce2c846d844b79a6ff054bb6c209d1f4653a26d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-a-symbol39s-numeric-value"></a>Ändern eines Symbols &#39; s numerischen Wert
Mit einer einzelnen Ressource verknüpfte Symbole, Sie können für die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) um den Symbolwert zu ändern. Sie können die [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md) so ändern Sie den Wert von Symbolen wird derzeit nicht auf eine Ressource zugewiesen. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  
### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>So ändern Sie einen zu einer einzelnen Ressource oder einem Objekt zugewiesenen Symbolwert  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der **Eigenschaften** geben den Symbolnamen, gefolgt von einem Gleichheitszeichen und eine ganze Zahl in die **ID** Feld, z. B.:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 Der neue Wert wird in der Symbolheaderdatei gespeichert, wenn Sie das nächste Mal das Projekt speichern. Nur der Symbolnamen verbleibt weiterhin im Feld „ID“ sichtbar. Nach der Überprüfung werden das Gleichheitszeichen und der Wert nicht mehr angezeigt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)aus.  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Beschränkungen für Symbolwerte](../windows/symbol-value-restrictions.md)   
 [Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)
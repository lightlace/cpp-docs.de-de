---
title: "Ändern eines Symbols oder Symbolnamens (ID) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.changing
dev_langs: C++
helpviewer_keywords:
- symbol names
- symbols, names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0ed56fc3663b99af311c52e463bd2f16fcef0a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Ändern eines Symbols oder Symbolnamens (ID)
Wenn Sie eine neue Ressource oder ein Ressourcenobjekt erstellen, weist die Entwicklungsumgebung einen standardmäßigen Symbolnamen zu, beispielsweise IDD_DIALOG1. Sie können die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) um den standardmäßigen Symbolnamen zu ändern oder den Namen eines beliebigen bereits mit einer Ressource verknüpften Symbols ändern.  
  
### <a name="to-change-a-resources-symbol-name"></a>So ändern Sie den Symbolname einer Ressource  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der **Eigenschaften** Fenster, geben Sie einen neuen Symbolnamen ein, oder wählen Sie aus der Liste der vorhandenen Symbole in der **ID** Feld.  
  
     Wenn Sie einen neuen Symbolnamen eingeben, wird diesem automatisch ein Wert zugewiesen.  
  
 Sie können die [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md) die Namen der derzeit nicht auf eine Ressource zugewiesenen Symbole zu ändern. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).  
  

  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md)   
 [Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)
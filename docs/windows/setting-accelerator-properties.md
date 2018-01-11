---
title: Festlegen von Zugriffstasteneigenschaften | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83eea84c89a9f9873b687333b7454d9f3c9c41b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setting-accelerator-properties"></a>Festlegen von Eigenschaften für Zugriffstasten
Festlegen von Zugriffstasteneigenschaften der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können zudem den Tastenkombinations-Editor verwenden, um die Tastenkombinationseigenschaften in der Tastenkombinationstabelle zu ändern. Mithilfe des Fensters „Eigenschaften“ oder des Tastenkombinations-Editors vorgenommene Änderungen führen zum gleichen Ergebnis: Die Bearbeitungen werden sofort in der Tastenkombinationstabelle berücksichtigt.  
  
 Es gibt drei Eigenschaften für jede Zugriffstaste [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   Die [Eigenschaft "Modifizierer"](../windows/accelerator-modifier-property.md) legt Steuerelement Tastenkombinationen für die Zugriffstaste.  
  
    > [!NOTE]
    >  Im Fenster „Eigenschaften“ wird diese Eigenschaft in Form von drei getrennten booleschen Werten angezeigt, wobei alle davon unabhängig gesteuert werden können: ALT, STRG und die UMSCHALTTASTE.  
  
-   Die [Schlüsseleigenschaft](../windows/accelerator-key-property.md) legt den tatsächlichen Schlüssel als Zugriffstaste verwendet.  
  
-   Die [Objekttypeigenschaft](../windows/accelerator-type-property.md) bestimmt, ob die Taste als virtuell (VIRTKEY) oder als ASCII/ANSI interpretiert wird.  
  

  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)   
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)
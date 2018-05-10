---
title: Festlegen von Zugriffstasteneigenschaften | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5198fc1958863d3b5ad560ffeb8c5576506e9e46
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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
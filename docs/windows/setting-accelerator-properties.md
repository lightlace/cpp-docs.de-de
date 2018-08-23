---
title: Festlegen von Zugriffstasteneigenschaften | Microsoft-Dokumentation
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
ms.openlocfilehash: 5d47dffb782da1094c157a7bbd21c40ab6ba9fef
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606703"
---
# <a name="setting-accelerator-properties"></a>Festlegen von Eigenschaften für Zugriffstasten

Sie können die Eigenschaften für Zugriffstasten festlegen, der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können auch die **Accelerator** -Editor, um die tastenkombinationseigenschaften in der tastenkombinationstabelle zu ändern. Änderungen, die mit der **Eigenschaften** Fenster oder der **Accelerator** Editor aufweisen, das gleiche Ergebnis: Änderungen werden sofort in der tastenkombinationstabelle dargestellt.

Es gibt drei Eigenschaften für jede Zugriffstaste [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160):

- Die [Eigenschaft "Modifizierer"](../windows/accelerator-modifier-property.md) legt die Steuerelement-Tastenkombinationen für die Zugriffstaste fest.

   > [!NOTE]
   > In der **Eigenschaften** Fenster, diese Eigenschaft wird als drei separate boolesche Eigenschaften, alle davon unabhängig gesteuert werden können: **Alt**, **STRG**, und **UMSCHALT**.

- Die [Schlüsseleigenschaft](../windows/accelerator-key-property.md) wird die eigentliche Taste als Zugriffstaste verwenden.

- Die [Type-Eigenschaft](../windows/accelerator-type-property.md) bestimmt, ob die Taste als virtuell (VIRTKEY) oder als ASCII/ANSI interpretiert wird.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)  
[Ressourcen-Editor](../windows/resource-editors.md)  
[Zugriffstasten-Editor](../windows/accelerator-editor.md)
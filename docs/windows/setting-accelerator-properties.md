---
title: Festlegen von Eigenschaften für Zugriffstasten (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
ms.openlocfilehash: 47ebd54fdaff099e3a8ce828581a66b0ec871915
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647017"
---
# <a name="setting-accelerator-properties"></a>Festlegen von Eigenschaften für Zugriffstasten

Sie können die Eigenschaften für Zugriffstasten festlegen, der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können auch die **Accelerator** -Editor, um die tastenkombinationseigenschaften in der tastenkombinationstabelle zu ändern. Änderungen, die mit der **Eigenschaften** Fenster oder der **Accelerator** Editor aufweisen, das gleiche Ergebnis: Änderungen werden sofort in der tastenkombinationstabelle dargestellt.

Es gibt drei Eigenschaften für jede ID der Zugriffstaste:

- Die [Eigenschaft "Modifizierer"](../windows/accelerator-modifier-property.md) legt die Steuerelement-Tastenkombinationen für die Zugriffstaste fest.

   > [!NOTE]
   > In der **Eigenschaften** Fenster, diese Eigenschaft wird als drei separate boolesche Eigenschaften, alle davon unabhängig gesteuert werden können: **Alt**, **STRG**, und **UMSCHALT**.

- Die [Schlüsseleigenschaft](../windows/accelerator-key-property.md) wird die eigentliche Taste als Zugriffstaste verwenden.

- Die [Type-Eigenschaft](../windows/accelerator-type-property.md) bestimmt, ob die Taste als virtuell (VIRTKEY) oder als ASCII/ANSI interpretiert wird.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Zugriffstasten-Editor](../windows/accelerator-editor.md)
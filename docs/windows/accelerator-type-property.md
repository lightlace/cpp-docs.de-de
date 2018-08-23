---
title: Accelerator-Type-Eigenschaft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59fae6d0809e32883d5d56e43e64525e23643d91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602325"
---
# <a name="accelerator-type-property"></a>Eigenschaft "Typ" von Zugriffstasten

Die Zugriffstaste **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der ID der Zugriffstaste verknüpft ist eine virtuelle Tastenkombination oder einen ASCII/ANSI-Schlüsselwert ist:

- Wenn die **Typ** -Eigenschaft ist ASCII, die [Modifizierer](../windows/accelerator-modifier-property.md) möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste verwendet die **STRG** Schlüssel (angegeben durch den Schlüssel mit dem vorherigen eine `^`).

- Wenn die **Typ** -Eigenschaft ist VIRTKEY, eine beliebige Kombination von `Modifier` und `Key` Werte gilt.

   > [!NOTE]
   > Wenn Sie verwenden möchten, geben einen Wert in die Zugriffstastentabelle, und den Wert als ASCII/ANSI, klicken Sie behandelt werden die **Typ** für den Eintrag in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** im Menü) an die `Key`, müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY ASCII *vor* eingeben der `Key` Code.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Festlegen von Eigenschaften für Zugriffstasten](../windows/setting-accelerator-properties.md)  
[Zugriffstasten-Editor](../windows/accelerator-editor.md)
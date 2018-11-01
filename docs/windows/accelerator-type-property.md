---
title: Accelerator-Type-Eigenschaft (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
ms.openlocfilehash: 00699f31b821aa508feec9ffe062d768f27ee5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475584"
---
# <a name="accelerator-type-property-c"></a>Accelerator-Type-Eigenschaft (C++)

Die Zugriffstaste **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der ID der Zugriffstaste verknüpft ist eine virtuelle Tastenkombination oder einen ASCII/ANSI-Schlüsselwert ist:

- Wenn die **Typ** -Eigenschaft ist ASCII, die [Modifizierer](../windows/accelerator-modifier-property.md) möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste verwendet die **STRG** Schlüssel (angegeben durch den Schlüssel mit dem vorherigen eine `^`).

- Wenn die **Typ** -Eigenschaft ist VIRTKEY, eine beliebige Kombination von `Modifier` und `Key` Werte gilt.

   > [!NOTE]
   > Wenn Sie verwenden möchten, geben einen Wert in die Zugriffstastentabelle, und den Wert als ASCII/ANSI, klicken Sie behandelt werden die **Typ** für den Eintrag in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** im Menü) an die `Key`, müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY ASCII *vor* eingeben der `Key` Code.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Festlegen von Eigenschaften für Zugriffstasten](../windows/setting-accelerator-properties.md)<br/>
[Zugriffstasten-Editor](../windows/accelerator-editor.md)
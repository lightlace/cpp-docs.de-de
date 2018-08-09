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
ms.openlocfilehash: da825a4f2052f05b24ff724d709c7c8a4b6a3db3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645684"
---
# <a name="accelerator-type-property"></a>Eigenschaft "Typ" von Zugriffstasten
Die Zugriffstaste **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der ID der Zugriffstaste verknüpft ist eine virtuelle Tastenkombination oder einen ASCII/ANSI-Schlüsselwert ist:  
  
-   Wenn die **Typ** -Eigenschaft ist ASCII, die [Modifizierer](../windows/accelerator-modifier-property.md) möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste verwendet die **STRG** Schlüssel (angegeben durch den Schlüssel mit dem vorherigen eine `^`).  
  
-   Wenn die **Typ** -Eigenschaft ist VIRTKEY, eine beliebige Kombination von `Modifier` und `Key` Werte gilt.  
  
    > [!NOTE]
    >  Wenn Sie verwenden möchten, geben einen Wert in die Zugriffstastentabelle, und den Wert als ASCII/ANSI, klicken Sie behandelt werden die **Typ** für den Eintrag in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** im Menü) an die `Key`, müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY ASCII *vor* eingeben der `Key` Code.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)
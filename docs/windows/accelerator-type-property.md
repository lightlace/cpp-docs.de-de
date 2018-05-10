---
title: Accelerator-Typeigenschaft | Microsoft Docs
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
ms.openlocfilehash: cb1ba8f117fadab7cccb835ba8889d57bcc9f184
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="accelerator-type-property"></a>Eigenschaft "Typ" von Zugriffstasten
Die Zugriffstaste **Typ** -Eigenschaft bestimmt, ob die Tastenkombination der Accelerator-ID zugeordnet, eine virtuelle Tastenkombination oder ein ASCII/ANSI-Schlüsselwert ist:  
  
-   Wenn die **Typ** Eigenschaft ist **ASCII**, die [Modifizierer](../windows/accelerator-modifier-property.md) möglicherweise keine nur oder ALT-Taste, oder es kann eine Zugriffstaste, die STRG-Taste verwendet, haben (gemäß den Schlüssel mit dem vorangehenden eine ^).  
  
-   Wenn die **Typ** Eigenschaft **VIRTKEY**, eine beliebige Kombination von und Tastenwerte ist gültig.  
  
    > [!NOTE]
    >  Wenn geben einen Wert in die Zugriffstastentabelle, und weisen den Wert, der als ASCII/ANSI behandelt werden sollen, klicken Sie einfach auf den Typ des Eintrags in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Allerdings bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** Menü) zum Angeben des Schlüssels müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY in ASCII *vor* Schlüssel eingeben.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)
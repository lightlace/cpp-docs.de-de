---
title: Accelerator-Typeigenschaft | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 214d8ca9c45a3657215833764268794b152bd337
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
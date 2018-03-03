---
title: -Attribut Kontexten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 662b540548c0594364bf11087c3b52420d29cf0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="attribute-contexts"></a>Attributkontexte
C++-Attribute können mit vier grundlegenden Felder beschrieben werden: das Ziel auf angewendet werden können kann (**gilt für**), wenn sie wiederholbar oder nicht sind (**Repeatable**), wird die Vorhandenseins anderer Attribute (erforderlich **Erforderliche Attribute**), und die Inkompatibilitäten mit anderen Attributen (**ungültige Attribute**). Diese Felder werden in einer zugehörigen Tabelle im Referenzthema für jedes Attribut aufgeführt. Jedes dieser Felder wird im folgenden beschrieben.  
  
## <a name="applies-to"></a>Gilt für  
 Dieses Feld beschreibt die verschiedenen C++ Sprachelemente, die rechtlichen Ziel für das angegebene Attribut sind. Z. B. wenn ein Attribut in "Class" gibt die **gilt für** Feld Dies gibt an, dass das Attribut nur auf eine rechtliche C++-Klasse angewendet werden kann. Wenn das Attribut auf eine Memberfunktion einer Klasse angewendet wird, führt ein Syntaxfehler.  
  
 Weitere Informationen finden Sie unter [Attribute nach Verwendung](../windows/attributes-by-usage.md).  
  
## <a name="repeatable"></a>Wiederholbar  
 Dieses Feld gibt an, ob das Attribut mehrmals für dasselbe Ziel angewendet werden kann. Die meisten Attribute nicht wiederholbar sind.  
  
## <a name="required-attributes"></a>Erforderliche Attribute  
 Dieses Feld Listet weitere Attribute, die müssen vorhanden (die auf dasselbe Ziel angewendet wird) für das angegebene Attribut ordnungsgemäß funktioniert. Ein Attribut aus, die Einträge für dieses Feld vorhanden ist.  
  
## <a name="invalid-attributes"></a>Ungültige Attribute  
 Dieses Feld Listet weitere Attribute, die mit dem angegebenen Attribut nicht kompatibel sind. Ein Attribut aus, die Einträge für dieses Feld vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Attributreferenz](../windows/cpp-attributes-reference.md)
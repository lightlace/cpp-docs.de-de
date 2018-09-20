---
title: Attribut Kontexten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f34fb2a019e922f7eed3a430e62be272f9d57dce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427289"
---
# <a name="attribute-contexts"></a>Attributkontexte
C++-Attribute können mithilfe von vier grundlegende Felder beschrieben werden: das Ziel, die sie auf angewendet werden können (**gilt für**), wenn sie wiederholbar oder nicht sind (**wiederholbare**), wird die Vorhandenseins anderer Attribute (erforderlich **Erforderliche Attribute**), und die Inkompatibilitäten mit anderen Attributen (**ungültige Attribute**). Diese Felder sind in einer zugehörigen Tabelle im Referenzthema für jedes Attribut des aufgeführt. Jedes dieser Felder wird unten beschrieben.
  
## <a name="applies-to"></a>Gilt für

Dieses Feld beschreibt die verschiedenen C++-Sprachelemente, die sind rechtliche Ziele für das angegebene Attribut. Z. B. wenn ein Attribut "Class" in gibt der **gilt für** Feld Dies gibt an, dass das Attribut nur auf eine rechtliche C++-Klasse angewendet werden kann. Wenn das Attribut auf eine Memberfunktion einer Klasse angewendet wird, führt ein Syntaxfehler.
  
Weitere Informationen finden Sie unter [Attribute nach Verwendung](../windows/attributes-by-usage.md).
  
## <a name="repeatable"></a>Wiederholbar

Dieses Feld gibt an, ob das Attribut mehrmals an dasselbe Ziel angewendet werden kann. Die meisten Attribute sind nicht wiederholbar.
  
## <a name="required-attributes"></a>Erforderliche Attribute

Dieses Feld Listet weitere Attribute, die sich für das angegebene Attribut ordnungsgemäß funktioniert (die an dasselbe Ziel angewendet werden) vorhanden. Es ist ungewöhnlich, dass ein Attribut aus, die Einträge für dieses Feld vorhanden sind.
  
## <a name="invalid-attributes"></a>Ungültige Attribute

Dieses Feld Listet weitere Attribute, die mit dem angegebenen Attribut nicht kompatibel sind. Es ist ungewöhnlich, dass ein Attribut aus, die Einträge für dieses Feld vorhanden sind.
  
## <a name="see-also"></a>Siehe auch

[C++-Attributreferenz](../windows/cpp-attributes-reference.md)
---
title: Memberzugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2aadccd883738fe2e6e9f57cc63f67cde6d6a6c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099940"
---
# <a name="member-access"></a>Memberzugriff

Klassenmemberzugriff kann gesteuert werden, durch überladen den Memberzugriffsoperator (**->**). Dieser Operator wird bei dieser Verwendung als unärer Operator betrachtet, und die überladene Operatorfunktion muss eine Klassenmemberfunktion sein. Daher ist die Deklaration für eine solche Funktion:

## <a name="syntax"></a>Syntax

```
class-type *operator->()
```

## <a name="remarks"></a>Hinweise

wo *Klassentyp* ist der Name der Klasse zu der dieser Operator gehört. Die Operatorfunktion für den Memberzugriff muss eine nicht statische Memberfunktion sein.

Dieser Operator wird (oft in Verbindung mit dem Zeiger-Dereferenzierungsoperator) verwendet, um "intelligente Zeiger" zu implementieren, die vor einer Dereferenzierung oder Zählung validiert werden.

Das Sprachelement **.** Memberzugriffsoperator kann werden nicht überladen.

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](../cpp/operator-overloading.md)
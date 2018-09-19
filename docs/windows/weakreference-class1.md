---
title: WeakReference Class1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9b7270a03192a6fcf53f0c2ecfd1af07a216243
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595530"
---
# <a name="weakreference-class1"></a>WeakReference Class1

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class WeakReference;
```

## <a name="remarks"></a>Hinweise

Stellt eine *schwachen Verweis* , die verwendet werden kann, mit der Windows-Runtime oder ein klassisches COM verwenden. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.

Ein **WeakReference** -Objekt verwaltet einen *starken Verweis*, dies ist ein Zeiger auf ein Objekt, und ein *starken Verweiszähler*, dies entspricht der Anzahl von Kopien der starke Referenz, die von verteilt wurden die `Resolve()` Methode. Obwohl die Anzahl der starken Verweis ungleich NULL ist, der starke Verweis gültig ist und das Objekt zugegriffen werden kann. Wird die Anzahl der starken Verweis auf 0 (null), wird der starke Verweis ungültig ist, und das Objekt kann nicht zugegriffen werden.

Ein **WeakReference** Objekt wird normalerweise verwendet, um ein Objekt darstellt, dessen Vorhandensein durch einen externen Thread oder Anwendung gesteuert wird. Erstellen Sie z. B. eine **WeakReference** Objekt aus einem Verweis auf ein Dateiobjekt. Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.

Die **WeakReference** Methoden sind threadsicher.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[WeakReference::WeakReference-Konstruktor](../windows/weakreference-weakreference-constructor.md)|Initialisiert eine neue Instanz der dem **WeakReference** Klasse.|
|[WeakReference::~WeakReference-Destruktor](../windows/weakreference-tilde-weakreference-destructor.md)|Hebt die Initialisierung (löscht) der aktuellen Instanz von der **WeakReference** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[WeakReference::DecrementStrongReference-Methode](../windows/weakreference-decrementstrongreference-method.md)|Dekrementiert den starken Verweiszähler des aktuellen **WeakReference** Objekt.|
|[WeakReference::IncrementStrongReference-Methode](../windows/weakreference-incrementstrongreference-method.md)|Inkrementiert die Anzahl der starken Verweis des aktuellen **WeakReference** Objekt.|
|[WeakReference::Resolve-Methode](../windows/weakreference-resolve-method.md)|Legt den angegebenen Zeiger auf den aktuellen Wert der starken Verweis fest, wenn die Anzahl der starken Verweis ungleich NULL ist.|
|[WeakReference::SetUnknown-Methode](../windows/weakreference-setunknown-method.md)|Den starken Verweis des aktuellen legt **WeakReference** Objekt, das den angegebenen Schnittstellenzeiger auf.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WeakReference`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
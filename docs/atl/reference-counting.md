---
title: (ATL) für die verweiszählung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e48cea73ede2a7c5ec529f4fc44f917494560ced
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751145"
---
# <a name="reference-counting"></a>Zählen der Verweise

COM selbst versucht automatisch nicht, ein Objekt aus dem Arbeitsspeicher entfernen, wenn er davon ausgeht, dass das Objekt nicht mehr verwendet wird. Stattdessen muss der Objektprogrammierer, das nicht verwendete Objekt entfernen. Der Programmierer bestimmt, ob ein Objekt basierend auf einen Verweiszähler entfernt werden kann.

COM verwendet die `IUnknown` Methoden ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) und [Version](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), um den Verweiszähler der Schnittstellen für ein Objekt zu verwalten. Die allgemeinen Regeln für das Aufrufen dieser Methoden sind:

- Wenn ein Client einen Schnittstellenzeiger, empfängt `AddRef` muss für die Schnittstelle aufgerufen werden.

- Wenn der Client mit den Schnittstellenzeiger auf abgeschlossen ist, muss er Aufrufen `Release`.

In einer einfachen Implementierung jedes `AddRef` aufrufen, inkrementiert bzw. jede `Release` aufrufen, wird eine Counter-Variable innerhalb des Objekts. Wenn die Anzahl auf 0 (null) zurückgegeben wird, wird die Schnittstelle nicht mehr hat alle Benutzer und selbst aus dem Arbeitsspeicher entfernen kann.

Verweiszählung kann auch implementiert werden, damit an, dass jeder Verweis auf das Objekt (nicht zu einer einzelnen Schnittstelle) gezählt wird. In diesem Fall jeder `AddRef` und `Release` Aufrufen des Delegaten an eine zentrale Implementierung für das Objekt und `Release` das gesamte Objekt frei, wenn der Verweiszähler null erreicht.

> [!NOTE]
>  Wenn eine `CComObject`-abgeleiteten Objekt wird erstellt, mit der **neue** -Operator, der Verweiszähler ist 0. Aus diesem Grund einen Aufruf `AddRef` müssen vorgenommen werden, nach erfolgreicher Erstellung der `CComObject`-abgeleitetes Objekt.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)   
[Verwalten der Lebensdauer von Objekten über die Verweiszählung](/windows/desktop/com/managing-object-lifetimes-through-reference-counting)


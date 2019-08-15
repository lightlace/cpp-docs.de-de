---
title: Verweis Zählung (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
ms.openlocfilehash: 565b74956280d4e80c41376ead4249e69980a80e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492222"
---
# <a name="reference-counting"></a>Verweis Zählung

Das com selbst versucht nicht automatisch, ein Objekt aus dem Arbeitsspeicher zu entfernen, wenn es meint, dass das Objekt nicht mehr verwendet wird. Der Objekt Programmierer muss stattdessen das nicht verwendete Objekt entfernen. Der Programmierer bestimmt, ob ein Objekt basierend auf einem Verweis Zähler entfernt werden kann.

COM verwendet die `IUnknown` Methoden, [adressf](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) und [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release), um den Verweis Zähler der Schnittstellen für ein Objekt zu verwalten. Die allgemeinen Regeln zum Aufrufen dieser Methoden lauten wie folgt:

- Wenn ein Client einen Schnittstellen Zeiger empfängt, `AddRef` muss für die-Schnittstelle aufgerufen werden.

- Wenn der Client den Schnittstellen Zeiger nicht mehr verwendet, muss er aufgerufen `Release`werden.

In einer einfachen Implementierung dekrementierungen jeder `AddRef` -Rückruf, und jeder `Release` -Befehl dekremenkt eine Counter-Variable innerhalb des-Objekts. Wenn die Anzahl auf 0 (null) zurückgesetzt wird, verfügt die Schnittstelle nicht mehr über Benutzer und kann sich selbst aus dem Arbeitsspeicher entfernen.

Die Verweis Zählung kann auch so implementiert werden, dass jeder Verweis auf das Objekt (nicht auf eine einzelne Schnittstelle) gezählt wird. In diesem Fall delegiert jeder `AddRef` - `Release` und-Rückruf an eine zentrale Implementierung für das-Objekt `Release` und gibt das gesamte-Objekt frei, wenn der Verweis Zähler Null erreicht.

> [!NOTE]
>  Wenn ein `CComObject`von abgeleitetes Objekt mit dem **New** -Operator erstellt wird, ist der Verweis Zähler 0. Daher `AddRef` muss nach der erfolgreichen Erstellung des `CComObject`von abgeleiteten Objekts ein-Rückruf durchgeführt werden.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[Verwalten von Objekt Lebensdauern durch Verweis Zählung](/windows/win32/com/managing-object-lifetimes-through-reference-counting)

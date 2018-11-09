---
title: Assistent zum Implementieren von Verbindungspunkten
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.impl.cp.overview
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
ms.openlocfilehash: b818a1a149e95805a8694f6c8d8d1325b33211b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531533"
---
# <a name="implement-connection-point-wizard"></a>Assistent zum Implementieren von Verbindungspunkten

Dieser Assistent implementiert einen Verbindungspunkt für ein COM-Objekt. Ein verbindungsfähiges Objekt (d.h. eine Quelle) kann einen Verbindungspunkt für seine eigenen Schnittstellen oder für Ausgangsschnittstellen zur Verfügung stellen. Visual C++ und Windows stellen Typbibliotheken bereit, die über Ausgangsschnittstellen verfügen. Jede Ausgangsschnittstelle kann von einem Client auf einem Objekt (d.h. eine Senke) implementiert werden.

Weitere Informationen finden Sie unter [ATL Connection Points (ATL-Verbindungspunkte)](../atl/atl-connection-points.md).

- **Verfügbare Typbibliotheken**

   Zeigt die verfügbaren Typbibliotheken an, die die Schnittstellendefinitionen enthalten, für die Sie Verbindungspunkte implementieren können. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei zu suchen, die die zu verwendende Typbibliothek enthält.

- **Position**

   Zeigt den Speicherort der Typbibliothek an, die in der Liste **Verfügbare Typbibliotheken** aktuell ausgewählt ist.

- **Schnittstellen**

   Zeigt die Schnittstellen an, deren Definitionen in der aktuell im Feld **Verfügbare Typbibliotheken** ausgewählten Typbibliothek enthalten sind.

   |Schaltfläche „Übertragen“|Beschreibung |
   |---------------------|-----------------|
   |**>**|Fügt den Namen der aktuell in der Liste **Schnittstellen** ausgewählten Schnittstelle der Liste **Verbindungspunkte implementieren** hinzu.|
   |**>>**|Fügt alle Namen der in der Liste **Schnittstellen** verfügbaren Schnittstellen der Liste **Verbindungspunkte implementieren** hinzu.|
   |**\<**|Entfernt den Namen der Schnittstelle, die aktuell in der Liste **Verbindungspunkte implementieren** ausgewählt ist.|
   |**\<\<**|Entfernt alle Namen der Schnittstellen, die aktuell in der Liste **Verbindungspunkte implementieren** aufgelistet sind.|

- **Verbindungspunkte implementieren**

   Zeigt den Namen der Schnittstellen an, für die Sie Verbindungspunkte implementieren, wenn Sie auf **Fertig stellen** klicken.

## <a name="see-also"></a>Siehe auch

[Implementieren eines Verbindungspunktes](../ide/implementing-a-connection-point-visual-cpp.md)
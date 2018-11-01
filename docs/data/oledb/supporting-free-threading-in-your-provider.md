---
title: Unterstützen des Freethreadings im Anbieter
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 653736b52c116f1c72856bf0c12e9deff05e0cfb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676199"
---
# <a name="supporting-free-threading-in-your-provider"></a>Unterstützen des Freethreadings im Anbieter

Alle OLE DB-Anbieterklassen sind threadsicher und Registrierungseinträge werden entsprechend festgelegt. Es ist eine gute Idee, freies threading zum bieten ein hohes Maß an Leistung in Situationen mit mehreren Benutzern zu unterstützen. Um Ihren Anbieter threadsicher zu schützen, müssen Sie sicherstellen, dass der Code ordnungsgemäß blockiert wird. Wenn Sie zu schreiben oder Speichern von Daten, müssen Sie den Zugriff auf kritische Abschnitte blockieren.

Einzelnen Vorlagenobjekte für OLE DB-Anbieter hat einen eigenen kritischen Abschnitt. Damit einfacher blockiert wird, muss jede neue Klasse, die Sie erstellen eine Vorlagenklasse, dauert die übergeordnete Klasse als Argument Name.

Das folgende Beispiel zeigt, wie Sie Ihren Code zu blockieren:

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

Weitere Informationen dazu, wie Sie kritische Abschnitte mit schützen `Lock` und `Unlock`, finden Sie unter [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

Sie müssen außerdem sicherstellen, dass alle Methoden außer Kraft setzen (wie z. B. `Execute`) sind threadsicher.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
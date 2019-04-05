---
title: Unterstützen des Freethreadings im Anbieter
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: a2afb7354dd0447375ee6205b7c5d9a4755aa4b8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025337"
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

Stellen Sie sicher, dass alle Methoden außer Kraft setzen (wie z. B. `Execute`) sind threadsicher.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
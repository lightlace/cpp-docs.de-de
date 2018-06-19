---
title: Unterstützen des Freethreadings im Anbieter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9c61aea0fec1f6d808a0a34ee74bd0ce2d399a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108513"
---
# <a name="supporting-free-threading-in-your-provider"></a>Unterstützen des Freethreadings im Anbieter
Die OLE DB-Anbieterklassen sind threadsicher und Registrierungseinträge werden entsprechend festgelegt. Es ist eine gute Idee, unterstützen Freethreadings so ein hohes Maß an Leistung in Situationen Mehrbenutzer bereitzustellen. Damit Ihr Anbieter Threadsicherheit bleibt, müssen Sie sicherstellen, dass der Code ordnungsgemäß blockiert wird. Bei jedem Schreiben oder Daten zu speichern, müssen Sie den Zugriff mit kritischen Abschnitten blockieren.  
  
 Einzelnen Vorlagenobjekte für OLE DB-Anbieter hat einen eigenen kritischen Abschnitt. Um blockierende einfacher zu machen, muss jede neue Klasse, die Sie erstellen eine Vorlagenklasse, die die übergeordnete Klasse dauert Name als Argument.  
  
 Im folgende Beispiel wird gezeigt, wie Code blockiert wird:  
  
```  
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
  
 Weitere Informationen zur Vorgehensweise beim Schützen von kritische Abschnitte mit `Lock` und `Unlock`, finden Sie unter [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Sie müssen auch sicherstellen, dass alle Methoden außer Kraft setzen (z. B. `Execute`) sind threadsicher.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
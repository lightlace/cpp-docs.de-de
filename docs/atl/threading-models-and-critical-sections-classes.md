---
title: Threading, Modelle und kritische Abschnitte-Klassen (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- vc.atl.threads.models
dev_langs:
- C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37172c0080664f496bdf5d5c7c0ebecbd8f77898
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="threading-models-and-critical-sections-classes"></a>Threading, Modelle und kritische Abschnitte-Klassen
Die folgenden Klassen definieren eine threading Modell- und kritischen Abschnitt:  
  
-   [CComModule](../atl/reference/catlautothreadmodule-class.md) implementiert einen Thread Pool, Apartmentmodell COM-Server.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) bietet Methoden zum Implementieren von eines Thread Pool Apartmentmodell COM-Servers.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) stellt Thread-sichere Methoden zum Inkrementieren und Dekrementieren eine Variable. Stellt einen kritischen Abschnitt.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) stellt Thread-sichere Methoden zum Inkrementieren und Dekrementieren eine Variable. Bietet kein kritischen Abschnitts.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) stellt Methoden zum Inkrementieren und Dekrementieren eine Variable. Bietet kein kritischen Abschnitts.  
  
-   [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) bestimmt die entsprechende Threadmodell Klasse für eine einzelnes Objekt-Klasse.  
  
-   [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) bestimmt die entsprechende Threadmodell Klasse für ein Objekt, das global verfügbar ist.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts. Der kritische Abschnitt wird automatisch initialisiert.  
  
-   ["CComCriticalSection"](../atl/reference/ccomcriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts. Der kritische Abschnitt muss explizit initialisiert werden.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) spiegelt die Methoden in `CComCriticalSection` ohne Angabe eines kritischen Abschnitts. Die Methoden in `CComFakeCriticalSection` nichts Unternehmen.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) veranschaulicht die Erstellungsfunktion für einen Thread CRT. Verwenden Sie diese Klasse, wenn der Thread CRT-Funktionen verwenden möchten.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) veranschaulicht die Erstellungsfunktion für einen Windows-Thread. Verwenden Sie diese Klasse, wenn der Thread CRT-Funktionen nicht verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)


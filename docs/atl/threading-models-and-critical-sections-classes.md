---
title: Threading, Modelle und kritische Abschnitte-Klassen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.threads.models
dev_langs: C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1501fe4f761b9bc8775018d6566ceff5fb0aa477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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


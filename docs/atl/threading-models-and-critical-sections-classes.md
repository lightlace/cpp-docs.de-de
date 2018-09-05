---
title: Klassen für Threadmodelle und kritische Klassen (ATL) | Microsoft-Dokumentation
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
ms.openlocfilehash: b87fdac5220ede47f1acf19088e952fde408a413
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755956"
---
# <a name="threading-models-and-critical-sections-classes"></a>Klassen für Threadmodelle und kritische Klassen

Die folgenden Klassen definieren eine threading-Modell und den kritischen Abschnitt:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) einen COM-Server in einem Thread-Pool, Apartment-Modell implementiert.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) bietet Methoden zum Implementieren eines COM-Servers in einem Thread-Pool, Apartment-Modell.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) threadsichere Methoden zum Inkrementieren und Dekrementieren eine Variable bereitgestellt. Stellt einen kritischen Abschnitt.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) threadsichere Methoden zum Inkrementieren und Dekrementieren eine Variable bereitgestellt. Bietet kein kritischen Abschnitts.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) bietet Methoden zum Inkrementieren und Dekrementieren eine Variable. Bietet kein kritischen Abschnitts.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) bestimmt die entsprechende threading-Modell-Klasse für ein einzelnes Objekt-Klasse.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) bestimmt die entsprechende threading-Modell-Klasse für ein Objekt, das global verfügbar ist.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts. Der kritische Abschnitt wird automatisch initialisiert.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) enthält Methoden zum Abrufen und Freigeben eines kritischen Abschnitts. Der kritische Abschnitt muss explizit initialisiert werden.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) spiegelt die Methoden in `CComCriticalSection` ohne Angabe eines kritischen Abschnitts. Die Methoden in `CComFakeCriticalSection` nichts Unternehmen.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) die Erstellungsfunktion für einen Thread für die CRT bietet. Verwenden Sie diese Klasse aus, wenn der Thread die CRT-Funktionen verwenden möchten.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) bietet die Erstellungsfunktion für einen Windows-Thread. Verwenden Sie diese Klasse aus, wenn der Thread nicht CRT-Funktionen nutzen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)


---
title: Ändern der Standardklassenfactory und Aggregationmodell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db2e684565589eb736b135db3460ed8b83d382b1
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850877"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Ändern der Standardklassenfactory und Aggregationmodell
ATL verwendet [CComCoClass](../atl/reference/ccomcoclass-class.md) das Klasse Factory und Aggregation Standardmodell für das Objekt zu definieren. `CComCoClass` Gibt an, die folgenden beiden Makros:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) deklariert die Klassenfactory sein [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können diese Standardeinstellungen überschreiben, indem Sie ein anderes Makro in der Klassendefinition angeben. Um beispielsweise verwenden [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) anstelle von `CComClassFactory`, geben Sie die [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) Makro:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Zwei andere Makros, die eine Klassenfactory zu definieren sind [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) und [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL verwendet auch die **Typedef** Mechanismus, um das Standardverhalten zu implementieren. Das Makro DECLARE_AGGREGATABLE verwendet z. B. **Typedef** zum Definieren eines Typs wird aufgerufen, `_CreatorClass`, die dann in der gesamten ATL verwiesen wird Beachten Sie, dass in einer abgeleiteten Klasse eine **Typedef** mit dem gleichen Namen wie der Basisklasse **Typedef** führt zu ATL, die die Definition und Überschreiben des Standardverhaltens.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation und Klassenfactory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)


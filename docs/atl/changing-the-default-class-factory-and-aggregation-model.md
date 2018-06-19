---
title: Ändern des Standard-Klassenfactory und Aggregation Modell | Microsoft Docs
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
ms.openlocfilehash: ce64f2162aa0d5cdf5bcf5e16b56b6989fcaf1ee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355238"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Ändern des Standard-Klassenfactory und Aggregation Modell
ATL verwendet [CComCoClass](../atl/reference/ccomcoclass-class.md) der Klasse Factory und Aggregation Standardmodell für Ihr Objekt definieren. `CComCoClass` Gibt die folgenden beiden Makros:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) deklariert die Klassenfactory sein [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können diese Standardeinstellungen überschreiben, indem Sie ein anderes Makro in der Klasse angeben. Beispielsweise verwenden [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) anstelle von `CComClassFactory`, geben Sie die [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) Makro:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Sind zwei Makros, die eine Klassenfactory definieren [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) und [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL verwendet auch die `typedef` Mechanismus, um das Standardverhalten zu implementieren. Z. B. die `DECLARE_AGGREGATABLE` Makro verwendet `typedef` zum Definieren eines Typs aufgerufen **_CreatorClass**, die dann in der gesamten ATL verwiesen wird Beachten Sie, dass in einer abgeleiteten Klasse eine `typedef` mit dem gleichen Namen wie der Basisklasse `typedef` ATL mithilfe Ihrer Definition und zum Überschreiben des Standardverhaltens führt.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ATL-COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation und Klassenfactory-Makros](../atl/reference/aggregation-and-class-factory-macros.md)


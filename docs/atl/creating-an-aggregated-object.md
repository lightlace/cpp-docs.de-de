---
title: Erstellen eines zusammengesetzten Objekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35ddbd6b8db853967a70de0427cc842689d55c82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-an-aggregated-object"></a>Erstellen eines zusammengesetzten Objekts
Aggregation Delegaten **IUnknown** aufruft, einen Zeiger auf des äußeren Objekts bereitstellen **IUnknown** auf das innere Objekt.  
  
### <a name="to-create-an-aggregated-object"></a>So erstellen ein zusammengesetztes Objekt  
  
1.  Hinzufügen einer **IUnknown** Zeiger auf die Klasse Objekt, und initialisieren Sie sie mit **NULL** im Konstruktor.  
  
2.  Überschreiben Sie [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) das Aggregat zu erstellen.  
  
3.  Verwenden der **IUnknown** -Zeiger ist, als der zweite Parameter für die in Schritt 1 definiert die [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) Makros.  
  
4.  Überschreiben Sie [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) zum Freigeben der **IUnknown** Zeiger.  
  
> [!NOTE]
>  Wenn Sie verwenden und eine Schnittstelle aus aggregierten Objekts während der freigeben `FinalConstruct`, sollten Sie Hinzufügen der [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) Makro, das die Definition der Klassenobjekts.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)


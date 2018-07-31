---
title: ODBC-Treiberanforderungen für Dynasets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d2b7d6d5f3bb0f88c8b46596309498b2d0529abb
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336500"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ODBC-Treiberanforderungen für Dynasets
In den MFC-ODBC-Datenbankklassen sind Dynasets Recordsets mit dynamischen Eigenschaften. Sie sind, mit der Datenquelle auf bestimmte Weise synchronisiert bleiben. MFC-Dynasets (aber nicht Forward-only-Recordsets) erfordern einen ODBC-Treiber mit der API-Ebene-2-Standards. Wenn der Treiber für Ihre [Datenquelle](../../data/odbc/data-source-odbc.md) entspricht der Ebene-1-API festlegen, können Sie trotzdem verwenden aktualisierbar und schreibgeschützt Momentaufnahmen und Forward-only-Recordsets, jedoch keine Dynasets. Ein Level 1-Treiber kann allerdings Dynasets unterstützen, wenn es sich um erweiterte FETCH- und keysetgesteuerte Cursor unterstützt.  
  
 In der ODBC-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet. Ein Cursor ist ein Mechanismus zum Verfolgen von seiner Position in einem Recordset. Weitere Informationen zu treiberanforderungen für Dynasets, finden Sie unter [Dynaset](../../data/odbc/dynaset.md). Weitere Informationen zu Cursorn finden Sie unter den [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/library/ms710252.aspx) -SDK in der MSDN-Dokumentation.  
  
> [!NOTE]
>  Der ODBC-Treiber muss für aktualisierbare Recordsets entweder positionierte Update-Anweisungen unterstützen oder die `::SQLSetPos` ODBC API-Funktion. Beide unterstützt, verwendet MFC `::SQLSetPos` für Effizienz. Alternativ können Sie für Momentaufnahmen, die Cursorbibliothek verwenden die die erforderliche Unterstützung für mit aktualisierbaren Momentaufnahmen (static-Cursor und positionierte Update-Anweisungen) bereitstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)
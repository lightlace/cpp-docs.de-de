---
title: "ODBC-Treiberanforderungen für Dynasets | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c444cd8e8d13cca7d891dba92e881b8ca167bbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ODBC-Treiberanforderungen für Dynasets
In den MFC-ODBC-Datenbankklassen sind Dynasets Recordsets mit dynamischen Eigenschaften. Sie sind, mit der Datenquelle auf bestimmte Weise synchronisiert bleiben. MFC-Dynasets (jedoch nicht Forward-only-Recordsets) erfordern einen ODBC-Treiber mit Level 2-API-Konformität. Wenn der Treiber für Ihre [Datenquelle](../../data/odbc/data-source-odbc.md) entspricht der Ebene-1-API festgelegt werden, noch können Sie aktualisierbar und schreibgeschützt sind und Momentaufnahmen und Forward-only-Recordsets, jedoch keine Dynasets. Level 1-Treiber kann allerdings Dynasets unterstützen, wenn es sich um erweiterte Fetch und keysetgesteuerte Cursor unterstützt.  
  
 In der ODBC-Terminologie werden Dynasets und Momentaufnahmen als Cursor bezeichnet. Ein Cursor ist ein Mechanismus zum Nachverfolgen der seine Position in einem Recordset. Weitere Informationen zu treiberanforderungen für Dynasets, finden Sie unter [Dynaset](../../data/odbc/dynaset.md). Weitere Informationen zu Cursorn finden Sie unter der [Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK in der MSDN-Dokumentation.  
  
> [!NOTE]
>  Der ODBC-Treiber muss für aktualisierbare Recordsets entweder positionierte Update-Anweisungen unterstützen oder die **:: SQLSetPos** ODBC API-Funktion. Wenn beide unterstützt, verwendet MFC **:: SQLSetPos** Gründen der Effizienz. Sie können auch für Momentaufnahmen können die Cursorbibliothek Sie die erforderliche Unterstützung für aktualisierbare Momentaufnahmen (statische Cursor und positionierte Update-Anweisungen) bietet.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)
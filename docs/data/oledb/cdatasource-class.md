---
title: CDataSource-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 508bbfc7551383fe1d4517d274031faef590fdb9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasource-class"></a>CDataSource-Klasse
Entspricht einer OLE DB-Datenquellenobjekt, das über einen Anbieter eine Verbindung mit einer Datenquelle darstellt.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDataSource  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/cdatasource-close.md)|Schließt die Verbindung.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Ruft die Initialisierungszeichenfolge der Datenquelle, die derzeit geöffnet ist.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Ruft die Werte der Eigenschaften, die derzeit für die verbundene Datenquelle festgelegt.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Ruft den Wert einer einzelnen Eigenschaft, die derzeit für die verbundene Datenquelle festgelegt.|  
|[Öffnen](../../data/oledb/cdatasource-open.md)|Erstellt eine Verbindung zu einem Anbieter (Datenquelle) entweder eine **CLSID**, **ProgID**, oder ein `CEnumerator` Moniker, die vom Aufrufer bereitgestellt.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Öffnet eine Datenquelle aus einer Datei, die durch den vom Benutzer bereitgestellten Dateinamen angegeben wird.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Öffnet die Datenquelle, die von einer Initialisierungszeichenfolge angegeben.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Ermöglicht es dem Benutzer um eine zuvor erstellte Datenverknüpfungsdatei, öffnen Sie die entsprechende Datenquelle auszuwählen.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Öffnet ein Datenquellenobjekt mithilfe des Dialogfelds Data Link.|  
  
## <a name="remarks"></a>Hinweise  
 Mindestens ein datenbanksitzungen können für eine einzelne Verbindung erstellt werden. Diese Sitzungen dargestellte `CSession`. Rufen Sie [CDataSource:: Open](../../data/oledb/cdatasource-open.md) zum Öffnen der Verbindung vor dem Erstellen einer Sitzungs mit `CSession::Open`.  
  
 Ein Beispiel zum Verwenden von `CDataSource`, finden Sie unter der [CatDB](../../visual-cpp-samples.md) Beispiel.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)
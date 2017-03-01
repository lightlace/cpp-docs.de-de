---
title: '&lt;system_error&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 43098f6f9276c9a66aaa7a30c95a6696e33f8429
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-functions"></a>&lt;System_error&gt;-Funktionen
||||  
|-|-|-|  
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|  
|[system_category](#system_category)|  
  
##  <a name="a-namegenericcategorya--genericcategory"></a><a name="generic_category"></a> generic_category  
 Stellt die Kategorie für allgemeine Fehler dar.  
  
```
extern const error_category& generic_category();
```  
  
### <a name="remarks"></a>Hinweise  
 Das `generic_categor`-Objekt ist eine Implementierung von [error-category](../standard-library/error-category-class.md).  
  
##  <a name="a-namemakeerrorcodea--makeerrorcode"></a><a name="make_error_code"></a> make_error_code  
 Erstellt ein Fehlercodeobjekt.  
  
```
error_code make_error_code(generic_errno _Errno);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errno`|Der im Fehlercodeobjekt zu speichernde Enumeration-Wert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fehlercodeobjekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemakeerrorconditiona--makeerrorcondition"></a><a name="make_error_condition"></a> make_error_condition  
 Erstellt ein Fehlerzustandobjekt.  
  
```
error_condition make_error_condition(generic_errno _Errno);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errno`|Der im Fehlerzustandobjekt zu speichernde Enumeration-Wert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fehlerzustandobjekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesystemcategorya--systemcategory"></a><a name="system_category"></a> system_category  
 Stellt die Kategorie für Fehler dar, die von Low-Level-Systemüberläufen verursacht wurden.  
  
```
extern const error_category& system_category();
```  
  
### <a name="remarks"></a>Hinweise  
 Das `system_categor`-Objekt ist eine Implementierung von [error-category](../standard-library/error-category-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [<system_error>](../standard-library/system-error.md)





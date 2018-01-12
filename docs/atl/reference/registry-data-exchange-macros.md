---
title: Registrierungsdaten Exchange Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
dev_langs: C++
helpviewer_keywords: RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0bc12c48ef628a42c309c44ce0fc37abda9b6690
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="registry-data-exchange-macros"></a>Registrierung Data Exchange-Makros
Diese Makros Registrierung Datenaustausch-Vorgänge.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.|  
|[END_RDX_MAP](#end_rdx_map)|Markiert das Ende der Zuordnung Registrierung Datenaustausch.|  
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag mit einer Variablen angegebene Element vom Typ BYTE.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ CString.|  
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ DWORD.|  
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable der TCHAR-Typ.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlplus.h  
   
##  <a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Hinweise  
 Die folgenden Makros werden in der Registrierung den Datenaustausch-Zuordnung zum Lesen und Schreiben von Einträgen in der systemregistrierung verwendet:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag mit einer Variablen angegebene Element vom Typ BYTE.|  
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ DWORD.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ CString.|  
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable der TCHAR-Typ.|  
  
 Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit demselben Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, wenn Code für den Datenaustausch zwischen der systemregistrierung implementiert werden muss und die Variablen, die in der RDX-Zuordnung angegeben werden.  
  
##  <a name="end_rdx_map"></a>END_RDX_MAP  
 Markiert das Ende der Zuordnung Registrierung Datenaustausch.  
  
```
END_RDX_MAP
```  
  
##  <a name="rdx_binary"></a>RDX_BINARY  
 Ordnet den angegebenen Registrierungseintrag mit einer Variablen angegebene Element vom Typ BYTE.  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parameter  
 `rootkey`  
 Die wichtigsten Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable, den angegebenen Registrierungseintrag zugeordnet werden soll.  
  
 `member_size`  
 Die Größe in Bytes, der die Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet werden soll. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit demselben Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der systemregistrierung und das Element ausführen Variablen in der RDX-Zuordnung.  
  
##  <a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ CString.  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parameter  
 `rootkey`  
 Die wichtigsten Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable, den angegebenen Registrierungseintrag zugeordnet werden soll.  
  
 `member_size`  
 Die Größe in Bytes, der die Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet werden soll. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit demselben Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der systemregistrierung und das Element ausführen Variablen in der RDX-Zuordnung.  
  
##  <a name="rdx_dword"></a>RDX_DWORD  
 Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable vom Typ DWORD.  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parameter  
 `rootkey`  
 Die wichtigsten Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable, den angegebenen Registrierungseintrag zugeordnet werden soll.  
  
 `member_size`  
 Die Größe in Bytes, der die Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet werden soll. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit demselben Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der systemregistrierung und das Element ausführen Variablen in der RDX-Zuordnung.  
  
##  <a name="rdx_text"></a>RDX_TEXT  
 Ordnet den angegebenen Registrierungseintrag mit einer angegebenen Membervariable der TCHAR-Typ.  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Parameter  
 `rootkey`  
 Die wichtigsten Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable, den angegebenen Registrierungseintrag zugeordnet werden soll.  
  
 `member_size`  
 Die Größe in Bytes, der die Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet werden soll. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit demselben Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der systemregistrierung und das Element ausführen Variablen in der RDX-Zuordnung.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)








---
title: "Registrierung der Makros für den Datenaustausch | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ee3c1d639ee4a6c6bd6cf26a8c59bb1a37a4fa02
ms.lasthandoff: 02/24/2017

---
# <a name="registry-data-exchange-macros"></a>Registrierung Data Exchange-Makros
Diese Makros Registrierung Data Exchange-Vorgänge.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.|  
|[END_RDX_MAP](#end_rdx_map)|Markiert das Ende der Zuordnung Registrierung Datenaustausch.|  
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag eine angegebene Membervariable vom Typ BYTE.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ CString.|  
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ DWORD.|  
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ TCHAR.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlplus.h  
   
##  <a name="a-namebeginrdxmapa--beginrdxmap"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Hinweise  
 Die folgenden Makros werden in der Registrierung den Datenaustausch-Zuordnung verwendet, zum Lesen und Schreiben von Einträgen in der Registrierung:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag eine angegebene Membervariable vom Typ BYTE.|  
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ DWORD.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ CString.|  
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ TCHAR.|  
  
 Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, sollte immer der Code muss auf den Datenaustausch zwischen der Registrierung und in der Zuordnung RDX angegebenen Variablen verwendet werden.  
  
##  <a name="a-nameendrdxmapa--endrdxmap"></a><a name="end_rdx_map"></a>END_RDX_MAP  
 Markiert das Ende der Zuordnung Registrierung Datenaustausch.  
  
```
END_RDX_MAP
```  
  
##  <a name="a-namerdxbinarya--rdxbinary"></a><a name="rdx_binary"></a>RDX_BINARY  
 Ordnet den angegebenen Registrierungseintrag eine angegebene Membervariable vom Typ BYTE.  
  
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
 Der Schlüssel Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable den angegebenen Eintrag zugeordnet.  
  
 `member_size`  
 Die Größe in Bytes, der Membervariablen.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der Registrierung und die Membervariablen in der Zuordnung RDX ausführen.  
  
##  <a name="a-namerdxcstringtexta--rdxcstringtext"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ CString.  
  
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
 Der Schlüssel Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable den angegebenen Eintrag zugeordnet.  
  
 `member_size`  
 Die Größe in Bytes, der Membervariablen.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der Registrierung und die Membervariablen in der Zuordnung RDX ausführen.  
  
##  <a name="a-namerdxdworda--rdxdword"></a><a name="rdx_dword"></a>RDX_DWORD  
 Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ DWORD.  
  
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
 Der Schlüssel Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable den angegebenen Eintrag zugeordnet.  
  
 `member_size`  
 Die Größe in Bytes, der Membervariablen.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der Registrierung und die Membervariablen in der Zuordnung RDX ausführen.  
  
##  <a name="a-namerdxtexta--rdxtext"></a><a name="rdx_text"></a>RDX_TEXT  
 Ordnet den angegebenen Registrierungseintrag einen angegebenen Membervariable vom Typ TCHAR.  
  
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
 Der Schlüssel Registrierungsstamm.  
  
 `subkey`  
 Der Registrierungsunterschlüssel.  
  
 `valuename`  
 Der Registrierungsschlüssel.  
  
 `member`  
 Die Membervariable den angegebenen Eintrag zugeordnet.  
  
 `member_size`  
 Die Größe in Bytes, der Membervariablen.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro wird verwendet, in Verbindung mit der `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros, einen bestimmten Registrierungseintrag eine Membervariable zugeordnet. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, indem die `BEGIN_RDX_MAP` und `END_RDX_MAP` Makros sollte verwendet werden, um den Austausch von Daten zwischen der Registrierung und die Membervariablen in der Zuordnung RDX ausführen.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)









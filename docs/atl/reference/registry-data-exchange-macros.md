---
title: Registrierung der Makros für den Datenaustausch | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlplus/ATL::BEGIN_RDX_MAP
- atlplus/ATL::END_RDX_MAP
- atlplus/ATL::RDX_BINARY
- atlplus/ATL::RDX_CSTRING_TEXT
- atlplus/ATL::RDX_DWORD
- atlplus/ATL::RDX_TEXT
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8a4ac19f9ead379b66d93a7be031bb53bc50fe5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109339"
---
# <a name="registry-data-exchange-macros"></a>Registrierungsdatenaustausch-Makros

Diese Makros führen Vorgänge aus Registrierung den Datenaustausch.

|||
|-|-|
|[BEGIN_RDX_MAP](#begin_rdx_map)|Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.|
|[END_RDX_MAP](#end_rdx_map)|Markiert das Ende der Zuordnung Registrierung den Datenaustausch.|
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ "BYTE".|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ CString.|
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ DWORD.|
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ TCHAR.|  

## <a name="requirements"></a>Anforderungen

**Header:** atlplus.h

##  <a name="begin_rdx_map"></a>  BEGIN_RDX_MAP

Markiert den Beginn der Registrierung den Datenaustausch Zuordnung.

```
BEGIN_RDX_MAP
```

### <a name="remarks"></a>Hinweise

Die folgenden Makros werden in der Registrierung den Datenaustausch-Zuordnung zum Lesen und Schreiben von Einträgen in der systemregistrierung verwendet:

|Makro|Beschreibung|
|-----------|-----------------|
|[RDX_BINARY](#rdx_binary)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ "BYTE".|
|[RDX_DWORD](#rdx_dword)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ DWORD.|
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ CString.|
|[RDX_TEXT](#rdx_text)|Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ TCHAR.|

Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen erstellt, durch die Makros BEGIN_RDX_MAP und END_RDX_MAP verwendet werden soll, wenn Ihr Code muss zum Austauschen von Daten zwischen der Registrierung des Systems und die Variablen, die in der Zuordnung RDX angegeben werden.

##  <a name="end_rdx_map"></a>  END_RDX_MAP

Markiert das Ende der Zuordnung Registrierung den Datenaustausch.

```
END_RDX_MAP
```

##  <a name="rdx_binary"></a>  RDX_BINARY

Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ "BYTE".

```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```

### <a name="parameters"></a>Parameter

*RootKey*<br/>
Der Schlüssel Registrierungsstamm.

*Unterschlüssel*<br/>
Der Registrierungsunterschlüssel.

*Wertname*<br/>
Der Registrierungsschlüssel.

*Member*<br/>
Die Membervariable des angegebenen Registrierungseintrags zugeordnet werden soll.

*member_size*<br/>
Die Größe in Bytes der Membervariable.

### <a name="remarks"></a>Hinweise

Dieses Makro wird in Verbindung mit den Makros BEGIN_RDX_MAP und END_RDX_MAP verwendet, um einen bestimmten Registrierungseintrag eine Membervariable zuzuordnen. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen, die durch die Makros BEGIN_RDX_MAP und END_RDX_MAP erstellt haben, führen Sie den Austausch von Daten zwischen der Registrierung des Systems und die Membervariablen verwendet werden soll in der RDX-Zuordnung.

##  <a name="rdx_cstring_text"></a>  RDX_CSTRING_TEXT

Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ CString.

```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```

### <a name="parameters"></a>Parameter

*RootKey*<br/>
Der Schlüssel Registrierungsstamm.

*Unterschlüssel*<br/>
Der Registrierungsunterschlüssel.

*Wertname*<br/>
Der Registrierungsschlüssel.

*Member*<br/>
Die Membervariable des angegebenen Registrierungseintrags zugeordnet werden soll.

*member_size*<br/>
Die Größe in Bytes der Membervariable.

### <a name="remarks"></a>Hinweise

Dieses Makro wird in Verbindung mit den Makros BEGIN_RDX_MAP und END_RDX_MAP verwendet, um einen bestimmten Registrierungseintrag eine Membervariable zuzuordnen. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen, die durch die Makros BEGIN_RDX_MAP und END_RDX_MAP erstellt haben, führen Sie den Austausch von Daten zwischen der Registrierung des Systems und die Membervariablen verwendet werden soll in der RDX-Zuordnung.

##  <a name="rdx_dword"></a>  RDX_DWORD

Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ DWORD.

```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```

### <a name="parameters"></a>Parameter

*RootKey*<br/>
Der Schlüssel Registrierungsstamm.

*Unterschlüssel*<br/>
Der Registrierungsunterschlüssel.

*Wertname*<br/>
Der Registrierungsschlüssel.

*Member*<br/>
Die Membervariable des angegebenen Registrierungseintrags zugeordnet werden soll.

*member_size*<br/>
Die Größe in Bytes der Membervariable.

### <a name="remarks"></a>Hinweise

Dieses Makro wird in Verbindung mit den Makros BEGIN_RDX_MAP und END_RDX_MAP verwendet, um einen bestimmten Registrierungseintrag eine Membervariable zuzuordnen. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen, die durch die Makros BEGIN_RDX_MAP und END_RDX_MAP erstellt haben, führen Sie den Austausch von Daten zwischen der Registrierung des Systems und die Membervariablen verwendet werden soll in der RDX-Zuordnung.

##  <a name="rdx_text"></a>  RDX_TEXT

Ordnet den angegebenen Registrierungseintrag eine angegebenen Member-Variable vom Typ TCHAR.

```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```

### <a name="parameters"></a>Parameter

*RootKey*<br/>
Der Schlüssel Registrierungsstamm.

*Unterschlüssel*<br/>
Der Registrierungsunterschlüssel.

*Wertname*<br/>
Der Registrierungsschlüssel.

*Member*<br/>
Die Membervariable des angegebenen Registrierungseintrags zugeordnet werden soll.

*member_size*<br/>
Die Größe in Bytes der Membervariable.

### <a name="remarks"></a>Hinweise

Dieses Makro wird in Verbindung mit den Makros BEGIN_RDX_MAP und END_RDX_MAP verwendet, um einen bestimmten Registrierungseintrag eine Membervariable zuzuordnen. Die globale Funktion [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), oder die Member-Funktion mit dem gleichen Namen, die durch die Makros BEGIN_RDX_MAP und END_RDX_MAP erstellt haben, führen Sie den Austausch von Daten zwischen der Registrierung des Systems und die Membervariablen verwendet werden soll in der RDX-Zuordnung.

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)


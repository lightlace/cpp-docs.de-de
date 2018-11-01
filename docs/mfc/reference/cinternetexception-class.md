---
title: CInternetException-Klasse
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: e89293d7b7803cf661bce7a91ea6df72b9a06122
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531572"
---
# <a name="cinternetexception-class"></a>CInternetException-Klasse

Stellt eine Ausnahmebedingung dar, die sich auf einen Internetvorgang bezieht.

## <a name="syntax"></a>Syntax

```
class CInternetException : public CException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|Erstellt ein `CInternetException`-Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|Der Kontextwert verknüpft ist, mit dem Vorgang, der die Ausnahme verursacht hat.|
|[CInternetException::m_dwError](#m_dwerror)|Der Fehler, der die Ausnahme verursacht hat.|

## <a name="remarks"></a>Hinweise

Die `CInternetException` Klasse enthält zwei öffentliche Datenmember: eine enthält den Fehlercode der Ausnahme zugeordnet, und der andere enthält den Kontextbezeichner des Internet-Anwendung, die dem Fehler zugeordnet.

Weitere Informationen zu Kontext-IDs für Internet-Anwendungen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

Diese Memberfunktion wird aufgerufen, wenn eine `CInternetException` Objekt erstellt wird.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parameter

*dwError*<br/>
Der Fehler, der die Ausnahme verursacht hat.

### <a name="remarks"></a>Hinweise

Rufen Sie die globale MFC-Funktion zum Auslösen einer CInternetException [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

Der Kontextwert, der dem entsprechenden Internet-Vorgang zugeordnet wird.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Hinweise

Der Kontextbezeichner wird ursprünglich in angegeben [CInternetSession](../../mfc/reference/cinternetsession-class.md) und übergeben von MFC zum [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-abgeleiteten Klassen. Sie können diesen Standardwert überschreiben, und weisen Sie einem *DwContext* Parameter einen Wert Ihrer Wahl. *DwContext* jeder Vorgang in das angegebene Objekt zugeordnet ist. *DwContext* identifiziert des Vorgangs der vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

Der Fehler, der die Ausnahme verursacht hat.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Hinweise

Dieser Fehlerwert kann ein System sein Fehlercode in WINERROR gefunden. H oder einen Fehlerwert aus WININET. H.

Eine Liste der Win32-Fehlercodes, finden Sie unter [Fehlercodes](/windows/desktop/Debug/system-error-codes). Eine Liste der Internet-spezifische Fehlermeldungen angezeigt werden soll finden Sie unter. Beide Themen werden im Windows SDK.

## <a name="see-also"></a>Siehe auch

[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)

---
title: Cinternettexception-Klasse
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
ms.openlocfilehash: c4f4c7a5b7594270aff9dfbc224e9a66ba09be3f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505905"
---
# <a name="cinternetexception-class"></a>Cinternettexception-Klasse

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
|[CInternetException::m_dwContext](#m_dwcontext)|Der Kontextwert, der dem Vorgang zugeordnet ist, der die Ausnahme verursacht hat.|
|[CInternetException::m_dwError](#m_dwerror)|Der Fehler, der die Ausnahme verursacht hat.|

## <a name="remarks"></a>Hinweise

Die `CInternetException` -Klasse enthält zwei öffentliche Datenmember: eine enthält den Fehlercode, der der Ausnahme zugeordnet ist, und die andere enthält den Kontext Bezeichner der Internet Anwendung, die dem Fehler zugeordnet ist.

Weitere Informationen zu Kontext Bezeichners für Internet Anwendungen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cinternetexception"></a>Cinternettexception:: cinternettexception

Diese Member-Funktion wird aufgerufen, `CInternetException` wenn ein-Objekt erstellt wird.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parameter

*dwError*<br/>
Der Fehler, der die Ausnahme verursacht hat.

### <a name="remarks"></a>Hinweise

Um eine cinterntexception auszulösen, nennen Sie die globale MFC-Funktion [afxthrowinternettexception](internet-url-parsing-globals.md#afxthrowinternetexception).

##  <a name="m_dwcontext"></a>Cinterverschachteltexception:: m_dwContext

Der Kontextwert, der dem verbundenen Internet Vorgang zugeordnet ist.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Hinweise

Der Kontext Bezeichner wird ursprünglich in [cinternetzession](../../mfc/reference/cinternetsession-class.md) angegeben und von MFC an [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)-und von [CInternetFile](../../mfc/reference/cinternetfile-class.md)abgeleitete Klassen übergeben. Sie können diese Standardeinstellung außer Kraft setzen und einem beliebigen *dwcontext* -Parameter einen Wert Ihrer Wahl zuweisen. *dwcontext* ist einem beliebigen Vorgang des angegebenen Objekts zugeordnet. *dwcontext* identifiziert die von [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)zurückgegebenen Statusinformationen des Vorgangs.

##  <a name="m_dwerror"></a>Cinterverschachteltexception:: m_dwError

Der Fehler, der die Ausnahme verursacht hat.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Hinweise

Dieser Fehlerwert kann ein Systemfehler Code sein, der in WinError gefunden wurde. H oder einen Fehlerwert aus WinInet. Micha.

Eine Liste der Win32-Fehlercodes finden Sie unter [Fehlercodes](/windows/win32/Debug/system-error-codes). Eine Liste der Internet spezifischen Fehlermeldungen finden Sie unter. Beide Themen sind im Windows SDK.

## <a name="see-also"></a>Siehe auch

[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)

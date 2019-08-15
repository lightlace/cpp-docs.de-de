---
title: CW2AEX-Klasse
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 4dda1cb9e54c44f7940475660bc629192b9ead61
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496269"
---
# <a name="cw2aex-class"></a>CW2AEX-Klasse

Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CT2AEX, CW2TEX, CW2CTEX und CT2CAEX sowie von typedef CW2A verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Parameter

*t_nBufferLength*<br/>
Die Größe des Puffers, der im Übersetzungsprozess verwendet wird. Die Standardlänge beträgt 128 Bytes.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Der Konstruktor.|
|[CW2AEX::~CW2AEX](#dtor)|Der Destruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX:: Operator LPSTR](#operator_lpstr)|Konvertierungs Operator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|Der Datenmember, der die Quell Zeichenfolge speichert.|
|[CW2AEX::m_szBuffer](#m_szbuffer)|Der statische Puffer, der zum Speichern der konvertierten Zeichenfolge verwendet wird.|

## <a name="remarks"></a>Hinweise

Wenn keine zusätzliche Funktionalität erforderlich ist, verwenden Sie CT2AEX, CW2TEX, CW2CTEX, CT2CAEX oder CW2A in Ihrem Code.

Diese Klasse enthält einen statischen Puffer fester Größe, der verwendet wird, um das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß für den statischen Puffer ist, ordnet die Klasse Arbeitsspeicher mithilfe von **malloc**zu und gibt den Arbeitsspeicher frei, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass diese Klasse im Gegensatz zu Text Konvertierungs Makros, die in früheren Versionen von ATL verfügbar waren, sicher in Schleifen verwendet werden kann und dass der Stapel nicht überläuft.

Wenn die Klasse versucht, Arbeitsspeicher auf dem Heap zuzuordnen, und einen Fehler verursacht `AtlThrow` , wird mit dem Argument E_OUTOFMEMORY aufgerufen.

Standardmäßig wird die ANSI-Codepage des aktuellen Threads für die Konvertierung von den ATL-Konvertierungs Klassen und-Makros verwendet. Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter für den Konstruktor für die Klasse an.

Die folgenden Makros basieren auf dieser Klasse:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Die folgende typedef basiert auf dieser Klasse:

- CW2A

Eine Erläuterung dieser Text Konvertierungs Makros finden Sie unter [ATL-und MFC-Zeichen folgen-Konvertierungs Makros](string-conversion-macros.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung dieser Zeichen folgen Konvertierungs Makros finden Sie unter [ATL-und MFC-Zeichen folgen Konvertierungs Makros](string-conversion-macros.md) .

## <a name="requirements"></a>Anforderungen

**Header:** ATL-v. h

##  <a name="cw2aex"></a>CW2AEX::CW2AEX

Der Konstruktor.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parameter

*psz*<br/>
Die zu konvertierende Text Zeichenfolge.

*nCodePage*<br/>
Die Codepage, die zum Ausführen der Konvertierung verwendet wird. Weitere Informationen finden Sie in der Code Page-Parameter Diskussion für die Windows SDK-Funktion " [multibytedewidechar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) ".

### <a name="remarks"></a>Hinweise

Weist den Puffer zu, der im Übersetzungsprozess verwendet wird.

##  <a name="dtor"></a>CW2AEX:: ~ CW2AEX

Der Destruktor.

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Hinweise

Gibt den zugewiesenen Puffer frei.

##  <a name="m_psz"></a>CW2AEX::m_psz

Der Datenmember, der die Quell Zeichenfolge speichert.

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>CW2AEX::m_szBuffer

Der statische Puffer, der zum Speichern der konvertierten Zeichenfolge verwendet wird.

```
char m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpstr"></a>CW2AEX:: Operator LPSTR

Konvertierungs Operator.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Text Zeichenfolge als LPSTR-Typ zurück.

## <a name="see-also"></a>Siehe auch

[CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)

---
title: CA2WEX-Klasse
ms.date: 11/04/2016
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
ms.openlocfilehash: 927b9f5031bb6262c2f4a071b535802eb9e6990a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497951"
---
# <a name="ca2wex-class"></a>CA2WEX-Klasse

Diese Klasse wird von den Zeichen folgen Konvertierungs Makros CA2TEX, CA2CTEX, CT2WEX und CT2CWEX sowie von typedef CA2W verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>Parameter

*t_nBufferLength*<br/>
Die Größe des Puffers, der im Übersetzungsprozess verwendet wird. Die Standardlänge beträgt 128 Bytes.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|Der Konstruktor.|
|[CA2WEX:: ~ CA2WEX](#dtor)|Der Destruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CA2WEX:: Operator LPWSTR](#operator_lpwstr)|Konvertierungs Operator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|Der Datenmember, der die Quell Zeichenfolge speichert.|
|[CA2WEX::m_szBuffer](#m_szbuffer)|Der statische Puffer, der zum Speichern der konvertierten Zeichenfolge verwendet wird.|

## <a name="remarks"></a>Hinweise

Wenn keine zusätzliche Funktionalität erforderlich ist, verwenden Sie CA2TEX, CA2CTEX, CT2WEX, CT2CWEX oder CA2W in Ihrem Code.

Diese Klasse enthält einen statischen Puffer fester Größe, der verwendet wird, um das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß für den statischen Puffer ist, ordnet die Klasse Arbeitsspeicher mithilfe von **malloc**zu und gibt den Arbeitsspeicher frei, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass diese Klasse im Gegensatz zu Text Konvertierungs Makros, die in früheren Versionen von ATL verfügbar waren, sicher in Schleifen verwendet werden kann und dass der Stapel nicht überläuft.

Wenn die Klasse versucht, Arbeitsspeicher auf dem Heap zuzuordnen, und einen Fehler verursacht `AtlThrow` , wird mit dem Argument E_OUTOFMEMORY aufgerufen.

Standardmäßig wird die ANSI-Codepage des aktuellen Threads für die Konvertierung von den ATL-Konvertierungs Klassen und-Makros verwendet. Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter für den Konstruktor für die Klasse an.

Die folgenden Makros basieren auf dieser Klasse:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Die folgende typedef basiert auf dieser Klasse:

- CA2W

Eine Erläuterung dieser Text Konvertierungs Makros finden Sie unter [ATL-und MFC-Zeichen folgen-Konvertierungs Makros](string-conversion-macros.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung dieser Zeichen folgen Konvertierungs Makros finden Sie unter [ATL-und MFC-Zeichen folgen Konvertierungs Makros](string-conversion-macros.md) .

## <a name="requirements"></a>Anforderungen

**Header:** ATL-v. h

##  <a name="ca2wex"></a>CA2WEX::CA2WEX

Der Konstruktor.

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parameter

*psz*<br/>
Die zu konvertierende Text Zeichenfolge.

*nCodePage*<br/>
Die Codepage, die zum Ausführen der Konvertierung verwendet wird. Weitere Informationen finden Sie in der Code Page-Parameter Diskussion für die Windows SDK-Funktion " [multibytedewidechar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) ".

### <a name="remarks"></a>Hinweise

Weist den Puffer zu, der im Übersetzungsprozess verwendet wird.

##  <a name="dtor"></a>CA2WEX:: ~ CA2WEX

Der Destruktor.

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Hinweise

Gibt den zugewiesenen Puffer frei.

##  <a name="m_psz"></a>CA2WEX::m_psz

Der Datenmember, der die Quell Zeichenfolge speichert.

```
LPWSTR m_psz;
```

##  <a name="m_szbuffer"></a>CA2WEX::m_szBuffer

Der statische Puffer, der zum Speichern der konvertierten Zeichenfolge verwendet wird.

```
wchar_t m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpwstr"></a>CA2WEX:: Operator LPWSTR

Konvertierungs Operator.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Text Zeichenfolge als LPWSTR-Typ zurück.

## <a name="see-also"></a>Siehe auch

[CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)<br/>
[CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)

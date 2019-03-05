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
ms.openlocfilehash: 97b398dd80bb38b1579458ae0b8b65f082458e23
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257916"
---
# <a name="cw2aex-class"></a>CW2AEX-Klasse

Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CT2AEX, CW2TEX, CW2CTEX, CT2CAEX wird und der Typedef CW2A verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Parameter

*t_nBufferLength*<br/>
Die Größe des Puffers, die in der Übersetzungsprozess verwendet werden soll. Die Standardeinstellung ist 128 Bytes.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Der Konstruktor.|
|[CW2AEX::~CW2AEX](#dtor)|Der Destruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX::Operator LPSTR](#operator_lpstr)|Konvertierungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|
|[CW2AEX::m_szBuffer](#m_szbuffer)|Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.|

## <a name="remarks"></a>Hinweise

Wenn zusätzliche Funktionalität erforderlich ist, verwenden Sie CT2AEX CW2TEX, CW2CTEX, CT2CAEX oder CW2A in Ihrem Code.

Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß, um in den statischen Puffer zu passen, weist die Klasse Speicher verwenden **Malloc**, den Speicher freigibt, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, dieser Klasse sicher in Schleifen verwendet werden kann und es der Stack overflow wird nicht verfügbar.

Wenn die Klasse versucht, die speicherbelegung auf dem Heap und ein Fehler auftritt, ruft sie `AtlThrow` mit einem Argument von E_OUTOFMEMORY.

Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung. Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage, als zweiten Parameter an den Konstruktor für die Klasse.

Die folgenden Makros basieren auf diese Klasse:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Die folgende Typedef basiert auf diese Klasse:

- CW2A

Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md).

## <a name="example"></a>Beispiel

Finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md) für ein Beispiel für diese Zeichenfolgen-konvertierungsmakros.

## <a name="requirements"></a>Anforderungen

**Header:** atlconv.h

##  <a name="cw2aex"></a>  CW2AEX::CW2AEX

Der Konstruktor.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parameter

*psz*<br/>
Die Textzeichenfolge, die konvertiert werden.

*nCodePage*<br/>
Die Codepage, die zum Durchführen der Konvertierung verwendet wird. Lesen Sie die Code-Seite Parameter Beiträge für die Windows SDK-Funktion [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar) Weitere Details.

### <a name="remarks"></a>Hinweise

Weist den Puffer, in der Übersetzungsprozess verwendet.

##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX

Der Destruktor.

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Hinweise

Gibt den zugeordneten Puffer frei.

##  <a name="m_psz"></a>  CW2AEX::m_psz

Der Datenmember, die die Quellzeichenfolge speichert.

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer

Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.

```
char m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CW2AEX::Operator LPSTR

Konvertierungsoperator.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Zeichenfolge zurück, LPSTR eingeben.

## <a name="see-also"></a>Siehe auch

[CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)

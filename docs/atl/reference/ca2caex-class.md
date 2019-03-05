---
title: CA2CAEX-Klasse
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: 88389d4fe913a31fce43e3c8cc95605f99701695
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326438"
---
# <a name="ca2caex-class"></a>CA2CAEX-Klasse

Diese Klasse wird von Zeichenfolgen-konvertierungsmakros CA2CTEX und CT2CAEX und der Typedef CA2CA verwendet.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>Parameter

*t_nBufferLength*<br/>
Die Größe des Puffers, die in der Übersetzungsprozess verwendet werden soll. Die Standardeinstellung ist 128 Bytes.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|Der Konstruktor.|
|[CA2CAEX::~CA2CAEX](#dtor)|Der Destruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CA2CAEX::Operator LPCSTR](#operator_lpcstr)|Konvertierungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|

## <a name="remarks"></a>Hinweise

Wenn zusätzliche Funktionalität erforderlich ist, verwenden Sie in Ihrem eigenen Code CA2CTEX, CT2CAEX oder CA2CA an.

Diese Klasse wird sicher in Schleifen verwendet, und es wird nicht zu einem Stapelüberlauf. Standardmäßig verwenden die ATL-Konvertierungsklassen und -makros für die Konvertierung die ANSI-Codeseite des aktuellen Threads.

Die folgenden Makros basieren auf diese Klasse:

- CA2CTEX

- CT2CAEX

Die folgende Typedef basiert auf diese Klasse:

- CA2CA

Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md).

## <a name="example"></a>Beispiel

Finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md) für ein Beispiel für diese Zeichenfolgen-konvertierungsmakros.

## <a name="requirements"></a>Anforderungen

**Header:** atlconv.h

##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX

Der Konstruktor.

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parameter

*psz*<br/>
Die Textzeichenfolge, die konvertiert werden.

*nCodePage*<br/>
Wenn Sie nicht in dieser Klasse verwendet.

### <a name="remarks"></a>Hinweise

Erstellt den Puffer für die Übersetzung erforderlich sind.

##  <a name="dtor"></a>  CA2CAEX:: ~ CA2CAEX

Der Destruktor.

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>Hinweise

Gibt den zugeordneten Puffer frei.

##  <a name="m_psz"></a>  CA2CAEX::m_psz

Der Datenmember, die die Quellzeichenfolge speichert.

```
LPCSTR m_psz;
```

##  <a name="operator_lpcstr"></a>  CA2CAEX::Operator LPCSTR

Konvertierungsoperator.

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Zeichenfolge zurück, LPCSTR eingeben.

## <a name="see-also"></a>Siehe auch

[CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)

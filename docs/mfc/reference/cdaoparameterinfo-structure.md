---
title: CDaoParameterInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 9f96cba8ea43db7e24e834b1de4ffb593b2c6e0d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303487"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo-Struktur

Die `CDaoParameterInfo`-Struktur enthält Informationen zu einem Parameter Objekt, das für Data Access Objects (DAO) definiert ist. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.

## <a name="syntax"></a>Syntax

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Benennt das Parameter Objekt eindeutig. Weitere Informationen finden Sie im Thema "Name Property" in der DAO-Hilfe.

*m_nType*<br/>
Ein-Wert, der den Datentyp eines Parameter Objekts angibt. Eine Liste der möglichen Werte finden Sie in der *m_nType* -Member der [cdaofieldinfo](../../mfc/reference/cdaofieldinfo-structure.md) -Struktur. Weitere Informationen finden Sie im Thema "Type Property" in der DAO-Hilfe.

*m_varValue*<br/>
Der Wert des-Parameters, der in einem [COleVariant](../../mfc/reference/colevariant-class.md) -Objekt gespeichert ist.

## <a name="remarks"></a>Hinweise

Die Verweise auf das primäre und sekundäre Replikat geben an, wie die Informationen von der [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) -Member-Funktion in der Klasse `CDaoQueryDef`zurückgegeben werden.

Die MFC-Klasse enthält keine DAO-Parameter Objekte in einer Klasse. DAO QueryDef-Objekte, die zugrunde liegenden MFC-`CDaoQueryDef` Objekten werden Parameter in ihren Parameter Sammlungen gespeichert. Um auf die Parameter Objekte in einem [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) -Objekt zuzugreifen, müssen Sie die `GetParameterInfo` Member-Funktion des QueryDef-Objekts für einen bestimmten Parameternamen oder einen Index in der Parameter Auflistung aufrufen. Sie können die Member-Funktion [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) zusammen mit `GetParameterInfo` verwenden, um die Parameter Auflistung zu durchlaufen.

Informationen, die von der [CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) -Member-Funktion abgerufen werden, werden in einer `CDaoParameterInfo` Struktur gespeichert. Aufrufen von `GetParameterInfo` für das Querydef-Objekt, in dessen Parameter Auflistung das Parameter Objekt gespeichert wird.

> [!NOTE]
>  Wenn Sie nur den Wert eines Parameters erhalten oder festlegen möchten, verwenden Sie die Element Funktionen [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) und [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) der Klasse `CDaoRecordset`.

`CDaoParameterInfo` definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können `Dump` verwenden, um den Inhalt eines `CDaoParameterInfo` Objekts zu speichern.

## <a name="requirements"></a>Voraussetzungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)

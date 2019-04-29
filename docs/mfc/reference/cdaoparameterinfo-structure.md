---
title: CDaoParameterInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 62addd44f8aa8fceafef6a27244994a2ec6b766b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399784"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo-Struktur

Die `CDaoParameterInfo` Struktur enthält Informationen über ein Parameterobjekt für Datenzugriffsobjekte (DAO) definiert.

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
Eindeutig benennt das Parameterobjekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*m_nType*<br/>
Ein Wert, der den Datentyp eines Parameterobjekts angibt. Eine Liste der möglichen Werte finden Sie die *M_nType* Mitglied der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Weitere Informationen finden Sie im Thema "Type-Eigenschaft" in-DAO-Hilfe.

*m_varValue*<br/>
Der Wert des Parameters, gespeichert einer [COleVariant](../../mfc/reference/colevariant-class.md) Objekt.

## <a name="remarks"></a>Hinweise

Die Verweise auf primären und sekundären Datenbank, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, indem die [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion in Klasse `CDaoQueryDef`.

MFC ist nicht mit DAO-Parameter-Objekte in einer Klasse gekapselt. DAO-Querydef Objekte die zugrunde liegenden MFC `CDaoQueryDef` Speichern von Objekten in ihren parameterauflistungen Parameter. Zugriff auf die Parameterobjekte in einer [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt, das Aufrufen des Objekts Querydef `GetParameterInfo` Member-Funktion für einen bestimmten Parameter-Namen oder ein Index in der Parameterauflistung. Können Sie die [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) Member-Funktion in Verbindung mit `GetParameterInfo` zum Durchlaufen der Parameterauflistung.

Informationen, die abgerufen, indem die [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Member-Funktion befindet sich in einem `CDaoParameterInfo` Struktur. Rufen Sie `GetParameterInfo` für das Querydef-Objekt, das in die Auflistung, deren Parameter den Parameter-Objekt wird gespeichert.

> [!NOTE]
>  Sollten Sie abrufen oder nur den Wert eines Parameters festzulegen, verwenden Sie die [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) und [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) Memberfunktionen der Klasse `CDaoRecordset`.

`CDaoParameterInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoParameterInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)

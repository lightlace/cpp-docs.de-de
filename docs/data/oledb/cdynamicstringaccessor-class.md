---
title: CDynamicStringAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
ms.openlocfilehash: 6ba56143beb3411734899839a46ab42992dfa4d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230994"
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor-Klasse

Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (die zugrunde liegende Struktur) verfügen.

## <a name="syntax"></a>Syntax

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[GetString](#getstring)|Ruft die Daten der angegebenen Spalte als Zeichenfolge ab.|
|[SetString](#setstring)|Legt die angegebene Spalte als Zeichenfolge fest.|

## <a name="remarks"></a>Hinweise

Während [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) fordert Daten in das systemeigene Format, die vom Anbieter gemeldeten `CDynamicStringAccessor` angefordert wird, dass der Anbieter alle Daten aus dem Datenspeicher als Zeichenfolgedaten abruft. Dies ist besonders nützlich für einfache Aufgaben, die Berechnung der Werte in den Datenspeicher, z. B. anzeigen oder drucken den Data Store Inhalt nicht benötigen.

Der systemeigene Typ des Daten der Spalte im Datenspeicher spielt keine Rolle. solange der Anbieter die Datenkonvertierung unterstützen kann, wird er die Daten in einem Format bereitstellen. Wenn der Anbieter die Konvertierung aus dem systemeigenen Datentyp in eine Zeichenfolge nicht unterstützt (die nicht üblich ist), der anfordernde Aufruf zurück, der Erfolgswert DB_S_ERRORSOCCURED und der Status für die entsprechende Spalte gibt ein Problem Konvertierung mit DBSTATUS_E_CANTCONVERTVALUE.

Verwendung `CDynamicStringAccessor` Methoden zum Abrufen der Spalteninformationen. Sie können diese Spalteninformationen verwenden, um einen Accessor dynamisch zur Laufzeit zu erstellen.

Die Spalteninformationen befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Abrufen von Daten aus dem Puffer mithilfe [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), oder das Speichern in den Puffer mit [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

Ausführliche Informationen und Beispiele für die Verwendung der dynamischen Accessorklassen, finden Sie unter [mithilfe von dynamischen Zugriffsmethoden](../../data/oledb/using-dynamic-accessors.md).

## <a name="getstring"></a> CDynamicStringAccessor::GetString

Ruft die Daten der angegebenen Spalte als Zeichenfolge ab.

### <a name="syntax"></a>Syntax

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Zeichenfolgenwert fest, die aus der angegebenen Spalte abgerufen werden. Der Wert ist vom Typ `BaseType`, der **CHAR** oder **WCHAR** je nachdem, ob _UNICODE oder nicht definiert ist. Gibt NULL zurück, wenn die angegebene Spalte nicht gefunden wird.

### <a name="remarks"></a>Hinweise

Die zweite außer Kraft setzen Form akzeptiert den Namen der Spalte als eine ANSI-Zeichenfolge an. Die dritte außer Kraft setzen Form akzeptiert den Namen der Spalte als Unicode-Zeichenfolge an.

## <a name="setstring"></a> CDynamicStringAccessor::SetString

Legt die angegebene Spalte als Zeichenfolge fest.

### <a name="syntax"></a>Syntax

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Der spezielle Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

*data*<br/>
[in] Ein Zeiger auf die Daten der Zeichenfolge, an die angegebene Spalte geschrieben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Zeichenfolgenwert fest, auf die angegebene Spalte festgelegt werden soll. Der Wert ist vom Typ `BaseType`, der **CHAR** oder **WCHAR** je nachdem, ob _UNICODE oder nicht definiert ist.

### <a name="remarks"></a>Hinweise

Das zweite überschreiben Form akzeptiert den Spaltennamen als ANSI-Zeichenfolge und das dritte überschreiben Form akzeptiert den Spaltennamen als Unicode-Zeichenfolge.

Wenn _SECURE_ATL definiert ist, um einen Wert ungleich NULL haben, wird ein Laufzeitfehler für die Assertion generiert, wenn die Eingabe *Daten* Zeichenfolge ist länger als die maximal zulässige Länge der Spalte auf den verwiesen wird. Andernfalls wird die Eingabezeichenfolge abgeschnitten, wenn er länger als die maximal zulässige Länge ist.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessorA-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CXMLAccessor-Klasse](../../data/oledb/cxmlaccessor-class.md)
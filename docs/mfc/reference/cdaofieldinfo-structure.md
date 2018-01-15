---
title: CDaoFieldInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoFieldInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fdab9bae7238f427ff2015beffd53570603af4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo-Struktur
Die `CDaoFieldInfo` Struktur enthält Informationen über ein Field-Objekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Eindeutig benennt das Feldobjekt. Details finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 `m_nType`  
 Ein Wert, der den Datentyp des Felds angibt. Details finden Sie im Thema "Typeigenschaft" DAO-Hilfe. Der Wert dieser Eigenschaft kann einen der folgenden sein:  
  
- **DbBoolean** Ja/Nein, wie **"true"**/**"false"**  
  
- **DbByte** Byte  
  
- **DbInteger** kurze  
  
- **DbLong** lang  
  
- **DbCurrency** Währung; Siehe MFC-Klasse [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **DbSingle** einzelne  
  
- **DbDouble** Double  
  
- **DbDate** Datum/Uhrzeit; Siehe MFC-Klasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **DbText** Text; Siehe MFC-Klasse [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **DbLongBinary** Long Binary (OLE-Objekt); Sie können die MFC-Klasse verwenden möchten [CByteArray](../../mfc/reference/cbytearray-class.md) anstelle Klasse `CLongBinary` als `CByteArray` zielgerichteteren und einfacher zu verwenden ist.  
  
- **Wert DbMemo** Memo; Siehe MFC-Klasse`CString`  
  
- **DbGUID** ein global eindeutiger Bezeichner/Universally Unique Identifier mit Remoteprozeduraufrufe verwendet. Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Verwenden Sie für binäre Daten nicht Zeichenfolgen-Datentypen. Dies bewirkt, dass Ihre Daten durch die Unicode/ANSI-Übersetzungsschicht, was zu höheren Aufwand und möglicherweise unerwartete Übersetzung übergeben.  
  
 *m_lSize*  
 Ein Wert, der die maximale Größe in Byte, ein DAO-Field-Objekt gibt an, die Text enthält oder die feste Größe von einem Field-Objekt, das Text oder numerische Werte enthält. Details finden Sie im Thema "Größeneigenschaft" DAO-Hilfe. Größen der folgenden Werte sind möglich:  
  
|Typ|Größe (Byte)|Beschreibung|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 Byte|Ja/Nein (identisch mit "true" / "false")|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Ganze Zahl|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Währung ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**DBDate fest**|8|Datum/Uhrzeit ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Text ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Lange Binärdatei (OLE-Objekts; [CByteArray](../../mfc/reference/cbytearray-class.md); verwenden Sie anstelle von `CLongBinary`)|  
|**Wert dbMemo**|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Ein global eindeutiger Bezeichner/universell eindeutige Bezeichner mit Remoteprozeduraufrufe verwendet.|  
  
 `m_lAttributes`  
 Gibt die Eigenschaften des ein Field-Objekt, das eine Tabledef, Recordset, Querydef oder Index-Objekt enthalten sind. Der zurückgegebene Wert kann eine Summe der folgenden Konstanten, erstellt mit dem C++-bitweise OR (**&#124;**) Operator:  
  
- **DbFixedField** die Feldgröße ist (Standardeinstellung für numerische Felder) fest.  
  
- **DbVariableField** die Feldgröße ist Variable (gilt nur für Textfelder).  
  
- **dbAutoIncrField festgelegt** der Wert des Felds für neue Datensätze wird automatisch erhöht, um eine eindeutige lange ganze Zahl, die nicht geändert werden kann. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.  
  
- **DbUpdatableField** kann der Wert des Felds geändert werden.  
  
- **DbDescending** Feld sortiert in absteigender (Z - A oder 0, 100) Reihenfolge (gilt nur für ein Field-Objekt in der Fields-Auflistung eines Objekts Index; in MFC können Objekte selbst in Objekten Objekte Tabledef enthaltenen sind Index). Wenn Sie diese Konstante weglassen, wird das Feld sortiert in aufsteigender (A - Z oder 0 - 100) Reihenfolge (Standard).  
  
 Wenn die Einstellung dieser Eigenschaft überprüft wird, können Sie die C++ bitweise- und Operator (**&**) für ein bestimmtes Attribut zu testen. Wenn Sie mehrere Attribute festlegen möchten, können kombinieren sie Sie durch die die entsprechenden Konstanten mit dem bitweisen OR-Kombination (**&#124;**) Operator. Details finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
 *m_nOrdinalPosition*  
 Ein Wert, der die numerische Reihenfolge angibt, in der ein Feld, das durch ein DAO-Field-Objekt dargestellt wird, relativ zu anderen Feldern angezeigt werden soll. Sie können diese Eigenschaft festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Details finden Sie im Thema "OrdinalPosition-Eigenschaft" DAO-Hilfe.  
  
 `m_bRequired`  
 Gibt an, ob ein DAO-Field-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft ist **"true"**, das Feld lässt sich nicht auf einen Null-Wert. Falls erforderlich ist, legen Sie auf **"false"**, das Feld darf Null-Werte als auch Werte, die durch die Einstellungen für die leere Zeichenfolge und ValidationRule-Eigenschaft angegebenen Bedingungen erfüllen. Details finden Sie im Thema "Erforderliche Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Gibt an, ob eine leere Zeichenfolge ("") ist ein gültiger Wert von DAO-Field-Objekt mit einem Text- oder Memo-Datentyp. Wenn diese Eigenschaft ist **"true"**, eine leere Zeichenfolge ist ein gültiger Wert. Sie können diese Eigenschaft festlegen, um **"false"** , stellen Sie sicher, dass Sie eine leere Zeichenfolge verwenden können, um den Wert eines Felds festzulegen. Details finden Sie im Thema "Leere Zeichenfolge-Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder sortieren. Details finden Sie im Thema "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe. Eine Liste der möglichen Werte zurückgegeben werden, finden Sie unter der **M_lCollatingOrder** Mitglied der [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Ein Wert, der den Namen des DAO-Field-Objekt in einer Fremdschlüsseltabelle in einer Beziehung angibt, die ein Feld in einer primären Tabelle entspricht. Details finden Sie im Thema "ForeignName Property" in der DAO-Hilfe.  
  
 *m_strSourceField*  
 Gibt den Namen des Felds, das die ursprüngliche Quelle der Daten für ein DAO-Field-Objekt durch eine Tabledef, Recordset oder DAO Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Feldnamen ein Field-Objekt zugeordnet. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu ermitteln, deren Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Weitere Informationen finden Sie im Thema "SourceField SourceTable-Eigenschaften" in der Hilfe von DAO ein. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Gibt den Namen der Tabelle, die die ursprüngliche Quelle der Daten für ein DAO-Field-Objekt durch eine Tabledef, Recordset oder DAO Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Tabellennamen ein Field-Objekt zugeordnet. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu ermitteln, deren Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Weitere Informationen finden Sie im Thema "SourceField SourceTable-Eigenschaften" in der Hilfe von DAO ein. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Ein Wert, der die Daten in einem Feld überprüft, da sie geändert oder einer Tabelle hinzugefügt. Details finden Sie im Thema "ValidationRule-Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Weitere Informationen über Tabledefs, finden Sie unter der **M_strValidationRule** Mitglied der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur.  
  
 `m_strValidationText`  
 Ein Wert, der den Text der Nachricht, in dem Ihre Anwendung angezeigt wird angibt, falls der Wert eines Objekts des DAO-Feld nicht die Gültigkeitsprüfungsregel durch die Einstellung der Eigenschaft ValidationRule angegeben erfüllen. Details finden Sie im Thema "ValidationText-Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 Der Standardwert von einer DAO-Field-Objekt. Wenn ein neuer Datensatz erstellt wird, wird die Einstellung der Eigenschaft "DefaultValue" automatisch als Wert für das Feld eingegeben. Details finden Sie im Thema "DefaultValue-Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primäre, sekundäre Datenbank und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die `GetFieldInfo` Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), und [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Feldobjekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen die DAO-Objekte, die zugrunde liegenden MFC-Objekte der folgenden Klassen umfassen tabellarische Auflistungen Feldobjekte: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), und [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Diese Klassen geben Memberfunktionen für den Zugriff auf einige Einzelelemente der Feldinformationen, oder Sie auf Sie zugreifen können alle gleichzeitig mit einem `CDaoFieldInfo` Objekt durch Aufrufen der `GetFieldInfo` Memberfunktion Rand des enthaltenden Objekts.  
  
 Neben dessen Verwendung zum Untersuchen von Objekteigenschaften, können Sie auch `CDaoFieldInfo` um einen Eingabeparameter für das Erstellen neuer Felder in einer Tabledef zu erstellen. Einfachere Optionen sind für diese Aufgabe zur Verfügung, aber wenn Sie eine genauere Steuerung des möchten, können Sie die Version des [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , akzeptiert eine `CDaoFieldInfo` Parameter.  
  
 Informationen, die abgerufen, indem die `GetFieldInfo` Member-Funktion (der Klasse, die das Feld enthält) befindet sich in einer `CDaoFieldInfo` Struktur. Rufen Sie die `GetFieldInfo` Memberfunktion Rand des enthaltenden Objekts in die Auflistung, deren Felder der Field-Objekt gespeichert wird. `CDaoFieldInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)


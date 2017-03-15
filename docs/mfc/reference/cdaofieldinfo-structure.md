---
title: CDaoFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 15db0c56480dfefb9fc8806c08596e37c7d38eb2
ms.lasthandoff: 02/24/2017

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
 Field-Objekt bezeichnet eindeutig. Details finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 `m_nType`  
 Ein Wert, der den Datentyp des Felds angibt. Details finden Sie im Thema "Typeigenschaft" DAO-Hilfe. Der Wert dieser Eigenschaft kann eine der folgenden sein:  
  
- **DbBoolean** Ja/Nein, wie **TRUE**/**FALSE**  
  
- **DbByte** Byte  
  
- **DbInteger** kurze  
  
- **DbLong** lang  
  
- **DbCurrency** Währung; Siehe MFC-Klasse [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **DbSingle** einzelne  
  
- **DbDouble** Double  
  
- **DbDate** Datum/Uhrzeit, finden Sie unter MFC-Klasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **DbText** Text; Siehe MFC-Klasse [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **DbLongBinary** Long Binary (OLE-Objekt), möglicherweise möchten Sie MFC-Klasse verwenden [CByteArray](../../mfc/reference/cbytearray-class.md) anstelle Klasse `CLongBinary` als `CByteArray` ist umfangreicher und einfacher zu verwenden.  
  
- **Wert DbMemo** Memo; Siehe MFC-Klasse`CString`  
  
- **DbGUID** ein global eindeutiger Bezeichner/Universally Unique Identifier für Remoteprozeduraufrufe verwendet. Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Verwenden Sie für binäre Daten keine Zeichenfolgen-Datentypen. Dies bewirkt, dass Ihre Daten über die Unicode/ANSI Übersetzungsschicht, was zu erhöhten Verwaltungsaufwand und möglicherweise unerwartete Übersetzung übergeben.  
  
 *m_lSize*  
 Ein Wert, der die maximale Größe in Bytes, der ein DAO-Field-Objekt gibt an, die Text oder feste Größe eines Field-Objekts, die Text oder numerische Werte enthält. Details finden Sie im Thema "Größeneigenschaft" DAO-Hilfe. Größe möglich der folgenden Werte:  
  
|Typ|Größe (Byte)|Beschreibung|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 Byte|Ja/Nein (identisch mit WAHR/FALSCH)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Ganze Zahl|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Währung ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Datum/Uhrzeit ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Text ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Long Binary (OLE-Objekt; [CByteArray](../../mfc/reference/cbytearray-class.md); verwenden Sie anstelle von `CLongBinary`)|  
|**Wert dbMemo**|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Ein global eindeutiger Bezeichner/Universally Unique Identifier für Remoteprozeduraufrufe verwendet.|  
  
 `m_lAttributes`  
 Gibt die Eigenschaften der enthaltenen eine Tabledef, Recordset, Querydef oder Index-Objekt ein Field-Objekt. Der zurückgegebene Wert kann eine Summe der folgenden Konstanten, erstellt mit dem C++-bitweises OR (**|**) Operator:  
  
- **DbFixedField** die Feldgröße ist fest (Standard für numerische Felder).  
  
- **DbVariableField** die Feldgröße ist variabel (nur Textfelder).  
  
- **dbAutoIncrField festgelegt** der Feldwert für neue Datensätze wird automatisch erhöht, um eine eindeutige lange ganze Zahl, die nicht geändert werden kann. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.  
  
- **DbUpdatableField** kann der Wert des Felds geändert werden.  
  
- **DbDescending** das Feld wird in absteigender sortiert (Z - A oder 100-0) Reihenfolge (gilt nur für ein Field-Objekt in eine Fields-Auflistung eines Index-Objekts, in MFC können Objekte sind selbst in Tabledef-Objekte enthalten Index). Wenn Sie diese Konstante auslassen, wird das Feld sortiert in aufsteigender (A - Z oder 0 - 100) Reihenfolge (Standard).  
  
 Bei der Prüfung der Einstellung dieser Eigenschaft können Sie die C++ bitweise- und Operator (**&**) für ein bestimmtes Attribut zu testen. Wenn Sie mehrere Attribute festlegen, können Sie Sie kombinieren, durch die Kombination der entsprechenden Konstanten mit dem bitweisen OR-(**|**) Operator. Details finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
 *m_nOrdinalPosition*  
 Ein Wert, der die numerische Reihenfolge angibt, in der ein Feld, das durch ein DAO-Field-Objekt dargestellt wird, relativ zu anderen Feldern angezeigt werden soll. Sie können diese Eigenschaft festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Details finden Sie unter dem Thema "OrdinalPosition-Eigenschaft" in der DAO-Hilfe.  
  
 `m_bRequired`  
 Gibt an, ob ein DAO-Field-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft ist **TRUE**, das Feld lässt sich nicht auf einen Null-Wert. Wenn erforderlich ist, legen Sie auf **FALSE**, kann das Feld enthalten, Null-Werte sowie die Werte, die die leere Zeichenfolge und ValidationRule-Eigenschaften angegebenen Kriterien erfüllen. Details finden Sie unter dem Thema "Erforderliche Eigenschaft" DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Gibt an, ob eine leere Zeichenfolge ("") ist ein gültiger Wert von DAO-Field-Objekt mit einem Text- oder Memo-Datentyp. Wenn diese Eigenschaft ist **TRUE**, eine leere Zeichenfolge ein gültiger Wert ist. Sie können diese Eigenschaft festlegen, um **FALSE** um sicherzustellen, dass Sie eine leere Zeichenfolge verwenden können, um den Wert eines Felds festzulegen. Details finden Sie unter dem Thema "Leere Zeichenfolge-Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder die Sortierung an. Details finden Sie unter "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe. Eine Liste der möglichen Werte zurückgegeben werden, finden Sie unter der **M_lCollatingOrder** Mitglied der [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Ein Wert, der den Namen des Objekts die DAO-Feld in einer Fremdtabelle in einer Beziehung angibt, die ein Feld in einer primären Tabelle entspricht. Details finden Sie im Thema "ForeignName Property" in der DAO-Hilfe.  
  
 *m_strSourceField*  
 Gibt den Namen des Felds, das die ursprüngliche Quelle der Daten für ein DAO-Feld-Objekt, eine Tabledef, Recordset oder Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Feldnamen ein Field-Objekt zugeordnet. Diese Eigenschaft können Sie z. B. die ursprüngliche Quelle der Daten in einem Abfragefeld ermitteln, dessen Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Details finden Sie im Thema "SourceField SourceTable-Eigenschaften" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Gibt den Namen der Tabelle, die die ursprüngliche Quelle der Daten für ein DAO-Feld-Objekt, eine Tabledef, Recordset oder Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Tabellennamen ein Field-Objekt zugeordnet. Diese Eigenschaft können Sie z. B. die ursprüngliche Quelle der Daten in einem Abfragefeld ermitteln, dessen Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Details finden Sie im Thema "SourceField SourceTable-Eigenschaften" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Ein Wert, der die Daten in einem Feld überprüft, wie es geändert oder einer Tabelle hinzugefügt. Details finden Sie unter dem Thema "ValidationRule-Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Weitere Informationen über Tabledefs finden Sie unter der **M_strValidationRule** Mitglied der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur.  
  
 `m_strValidationText`  
 Ein Wert, der den Text der Nachricht, die der Anwendung angezeigt angibt, wenn der Wert eines DAO Field-Objekts nicht durch die Einstellung der ValidationRule-Eigenschaft angegebenen erfüllt. Details finden Sie im Thema "ValidationText-Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 Der Standardwert eines DAO Field-Objekts. Wenn ein neuer Datensatz erstellt wird, wird die Einstellung der DefaultValue-Eigenschaft automatisch als der Wert für das Feld eingegeben. Details finden Sie unter dem Thema "DefaultValue-Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären, sekundären und alle oben anzugeben, wie die Informationen zurückgegeben werden, durch die `GetFieldInfo` -Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Field-Objekte werden nicht von einer MFC-Klasse dargestellt. Stattdessen enthalten die DAO-Objekte, die zugrunde liegenden MFC-Objekte der folgenden Klassen Sammlungen von Field-Objekten: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), und [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Diese Klassen Memberfunktionen für den Zugriff auf einige einzelne Elemente des Feldinformationen oder können sie gleichzeitig mit zugreifen ein `CDaoFieldInfo` -Objekt durch Aufrufen der `GetFieldInfo` -Memberfunktion des enthaltenden Objekts.  
  
 Neben seiner Verwendung zum Untersuchen von Objekteigenschaften, können Sie auch `CDaoFieldInfo` Eingabeparameter für das Erstellen neuer Felder in einer Tabledef erstellt. Einfachere Optionen stehen für diese Aufgabe, aber wenn Sie eine genauere Kontrolle wünschen, können die Version des [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , akzeptiert einen `CDaoFieldInfo` Parameter.  
  
 Informationen abgerufen werden, indem Sie die `GetFieldInfo` Member-Funktion (der Klasse, die das Feld enthält) befindet sich in einer `CDaoFieldInfo` Struktur. Rufen Sie die `GetFieldInfo` -Memberfunktion des enthaltenden Objekts, das in die Auflistung, deren Felder Field-Objekt gespeichert ist. `CDaoFieldInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoFieldInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)



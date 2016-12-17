---
title: "CDaoFieldInfo-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDaoFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Felderauflistung"
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoFieldInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoFieldInfo`\-Struktur enthält Informationen über ein Feldobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
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
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Feldobjekt.  Ausführliche Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_nType`  
 Ein Wert, der dem Datentyp des Felds angeben.  Ausführliche Informationen finden Sie im Thema "Typeigenschaft" in der DAO\-Hilfe.  Der Wert dieser Eigenschaft kann einen der folgenden Werte:  
  
-   **dbBoolean** ja\/nein, identisch **TRUE**\/**FALSE**  
  
-   **dbByte** Byte  
  
-   **dbInteger** kurz  
  
-   **dbLong** lang  
  
-   Währung **dbCurrency**; finden Sie MFC\-Klasse [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
-   **dbSingle** einzeln  
  
-   **dbDouble** Double  
  
-   **dbDate** Datum \/Uhrzeit; finden Sie MFC\-Klasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
-   **dbText** Text; finden Sie MFC\-Klasse [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
-   lange Binärdatei **dbLongBinary**\(OLE\-Objekt\); Sie sollten MFC\-Klasse [CByteArray](../../mfc/reference/cbytearray-class.md) anstelle der `CLongBinary`\-Klasse verwenden, da `CByteArray` umfangreicher und einfacher zu verwenden ist.  
  
-   **dbMemo** Memo; Sie finden eine `CString`  
  
-   **dbGUID** einen Globally Unique Identifier\/ein Universally Unique Identifier mit Remoteprozeduraufrufen.  Weitere Informationen finden Sie im Thema "Typeigenschaft" in der DAO\-Hilfe.  
  
> [!NOTE]
>  Verwenden Sie nicht für Zeichenfolgen\-Datentypen Binärdaten.  Dadurch werden die Daten, von der Unicode\-\/ANSIübersetzungsebene, Ergebnis des stärkeren Mehraufwand und möglicherweise der unerwarteten Übersetzung zu übergeben.  
  
 *m\_lSize*  
 Ein Wert, der die maximale Größe, in Bytes, eines DAO\-Feldobjekts angibt, das Text oder die feste Größe eines Feldobjekts enthält, das Text oder numerische Werte enthält.  Ausführliche Informationen finden Sie im Thema "Größen\-Eigenschaft" in der DAO\-Hilfe.  Größen können eine der folgenden Werte sein:  
  
|Typ|Größe \(Byte\)|**Beschreibung**|  
|---------|--------------------|----------------------|  
|**dbBoolean**|1 Byte|\(Ja\/Nein identisch True und False\)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Integer|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Währung \([COleCurrency](../../mfc/reference/colecurrency-class.md)\)|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Datum \/Uhrzeit \([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)\)|  
|**dbText**|1 \- 255|Text \([CString](../../atl-mfc-shared/reference/cstringt-class.md)\)|  
|**dbLongBinary**|0|Lange Binärdatei \(OLE\-Objekt; [CByteArray](../../mfc/reference/cbytearray-class.md); Verwendung anstelle von `CLongBinary`\)|  
|**dbMemo**|0|Memo \([CString](../../atl-mfc-shared/reference/cstringt-class.md)\)|  
|**dbGUID**|16|Ein Globally Unique Identifier\/ein Universally Unique Identifier mit Remoteprozeduraufrufen.|  
  
 `m_lAttributes`  
 Gibt die Eigenschaften eines Feldobjekts an, das durch eine, tabledef\- ein Recordset, eine Querydef oder ein Indexobjekt enthalten ist.  Der Wert, der zurückgegeben wird, kann eine Summe dieser Konstanten sein, erstellt mit dem C\+\+\-bitweisen OR \(  **&#124;**\) Operator:  
  
-   **dbFixedField** die Feldgröße behoben ist \(Standard für numerische Felder\).  
  
-   **dbVariableField** die Feldgröße ist variabel Textfelder \(nur\).  
  
-   **dbAutoIncrField** Der Feldwert für neue Datensätze wird automatisch zu einer eindeutigen lange ganze Zahl inkrementiert, die nicht geändert werden kann.  Nur unterstützt für Microsoft Jet\-Datenbank\-Tabellen.  
  
-   **dbUpdatableField** Der Feldwert kann geändert werden.  
  
-   **dbDescending** das Feld wird in Abstieg\(Z\-A oder 100 \- 0\) Reihenfolge sortiert \(gilt nur für ein Feldobjekt in einer Framesauflistung eines Indexobjekts zu; in MFC werden Indexobjekte selbst in den Tabledef\-Objekten enthalten\).  Wenn Sie diese Konstante weglassen, wird das Feld in aufsteigender \(A\-Z oder 0 \- 100\) Reihenfolge \(Standard\) sortiert.  
  
 Wenn Sie die Einstellung dieser Eigenschaft überprüfen, können Sie den Operator C\+\+\-bitweisenAND \(**&**\) können für ein bestimmtes Attribut zu testen.  Wenn Sie mehrere Attribute festlegen, können Sie sie miteinander kombinieren, indem Sie die erforderlichen Konstanten mit dem bitweisen Operator OR kombinieren \(  **&#124;**Operator.\)  Ausführliche Informationen finden Sie im Thema "Attribut\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_nOrdinalPosition*  
 Ein Wert, der der numerischen Reihenfolge angibt, in der ein Feld möchten, wurde von einem relativ zu anderen Feldern dar angezeigt werden, DAO\-Feldobjekt.  Sie können diese Eigenschaft mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  Ausführliche Informationen finden Sie im Thema "OrdinalPositions\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_bRequired`  
 Gibt an, ob ein DAO\-Feldobjekt einen Wert ungleich null ist.  Wenn diese Eigenschaft **TRUE** ist, kann das Feld keinen NULL\-Wert.  Bei Bedarf wird auf **FALSE** festgelegt, kann das Feld NULL\-Werte sowie Werte enthalten, die die Bedingungen erfüllen, die von der AllowZeroLength Eigenschafteneinstellungen und ValidationRule angegeben werden.  Ausführliche Informationen finden Sie, dass das Thema "Eigenschaft" in der DAO\-Hilfe erforderlich.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 *m\_bAllowZeroLength*  
 Gibt an, ob eine leere Zeichenfolge \(""\) ein gültiger Wert eines DAO\-Feldobjekts mit einem Text\- oder Memodatentyp ist.  Wenn diese Eigenschaft **TRUE** ist, ist eine leere Zeichenfolge ein gültiger Wert.  Sie können diese Eigenschaft auf **FALSE** festlegen, um sicherzustellen, dass eine leere Zeichenfolge nicht verwenden können, um den Wert eines Felds festzulegen.  Ausführliche Informationen finden Sie im Thema "AllowZeroLength\-Eigenschaft" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 `m_lCollatingOrder`  
 Gibt der Sequenz der Sortierreihenfolge im Text für Zeichenfolgenvergleiche oder Sortierung an.  Ausführliche Informationen finden Sie im Thema ", Windows\-Registrierungseinstellungen für Datenzugriff" in der DAO\-Hilfe anzupassen.  Eine Liste der möglichen zurückgegebenen Werte, finden Sie den **m\_lCollatingOrder**\-Member der Struktur. [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 `m_strForeignName`  
 Ein Wert, der, einer Beziehung, den Namen des DAO\-Feldobjekts in der fremden Tabelle angibt, die an ein Feld in einer Tabelle entspricht.  Ausführliche Informationen finden Sie im Thema "ForeignName\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strSourceField*  
 Gibt den Namen des Felds, das die ursprüngliche Quelle der Daten für ein DAO\-Feldobjekt ist, auf das eine, tabledef\- ein Recordset oder ein Querydef\-Objekt enthalten ist.  Diese Eigenschaft gibt den ursprünglichen Feldnamen an, der einem Feldobjekt zugeordnet ist.  Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten auf einem Abfragengebiet zu bestimmen, deren Name den Namen des Felds in der zugrunde liegenden Tabelle nicht verknüpft ist.  Ausführliche Informationen finden Sie im Thema "SourceField, SourceTable\-Eigenschaften" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 *m\_strSourceTable*  
 Gibt den Namen der Tabelle, die die ursprüngliche Quelle der Daten für ein DAO\-Feldobjekt ist, auf das eine, tabledef\- ein Recordset oder ein Querydef\-Objekt enthalten ist.  Diese Eigenschaft gibt den verwendet an, der einem Feldobjekt zugeordnet ist.  Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten auf einem Abfragengebiet zu bestimmen, deren Name den Namen des Felds in der zugrunde liegenden Tabelle nicht verknüpft ist.  Ausführliche Informationen finden Sie im Thema "SourceField, SourceTable\-Eigenschaften" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 `m_strValidationRule`  
 Ein Wert, der die Daten in einem Feld überprüft, das an eine Tabelle geändert oder hinzugefügt wird.  Ausführliche Informationen finden Sie im Thema "ValidationRule\-Eigenschaft" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 Weitere Informationen über Tabledefs, finden Sie den **m\_strValidationRule**\-Member der Struktur. [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)  
  
 `m_strValidationText`  
 Ein Wert, der den Text der Meldung angibt, die von der Anwendung, wenn der Wert eines DAO\-Feldobjekts nicht die Validierungsregel entspricht, die durch die ValidationRule\-Eigenschafteneinstellung angegeben wird.  Ausführliche Informationen finden Sie im Thema "ValidationText\-Eigenschaft" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
 *m\_strDefaultValue*  
 Der Standardwert eines DAO\-Feldobjekts.  Wenn ein neuer Datensatz erstellt wird, wird die DefaultValue\-Eigenschafteneinstellung automatisch während der Wert für das Feld eingegeben.  Ausführliche Informationen finden Sie im Thema "DefaultValue\-Eigenschaft" in der DAO\-Hilfe.  Sie können diese Eigenschaft für eine tabledef\- mit [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) festlegen.  
  
## Hinweise  
 Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die `GetFieldInfo`\-Memberfunktion in Klassen [CDaoTableDef](../Topic/CDaoTableDef::GetFieldInfo.md), [CDaoQueryDef](../Topic/CDaoQueryDef::GetFieldInfo.md) und [CDaoRecordset](../Topic/CDaoRecordset::GetFieldInfo.md) zurückgegeben werden.  
  
 Feldobjekte werden nicht durch eine MFC\-Klasse dargestellt.  Stattdessen enthält die DAO\-Objekte MFC\-Objekten, die der folgenden Klassen zugrunde liegen, Auflistungen Feldobjekte: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) und [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md).  Diese Klassenzubehörmemberfunktionen, die auf von einzelner Elemente der Feldinformationen zuzugreifen oder Sie können mit einem `CDaoFieldInfo`\-Objekt in einem gemeinsam zugreifen, indem sie die `GetFieldInfo`\-Memberfunktion des enthaltenden Objekts aufrufen.  
  
 Neben der Verwendung für die Untersuchung von Objekteigenschaften, können Sie `CDaoFieldInfo` auch verwenden, um einen Eingabeparameter für das Erstellen neuer Feldern in einer tabledef\- zu erstellen.  Einfachere Optionen sind für diese Aufgabe verfügbar, aber, wenn Sie detailliert steuern möchten, können Sie die Version von [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) verwenden, die einen `CDaoFieldInfo`\-Parameter akzeptiert.  
  
 Die Informationen, die von der `GetFieldInfo`\-Memberfunktion abgerufen werden \(der Klasse, die das Feld enthält\), werden in einer `CDaoFieldInfo`\-Struktur gespeichert.  Rufen Sie die Memberfunktion `GetFieldInfo` des enthaltenden Objekts auf, in dessen Framesauflistung das Feldobjekt gespeichert wird.  `CDaoFieldInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoFieldInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)   
 [CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)   
 [CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)
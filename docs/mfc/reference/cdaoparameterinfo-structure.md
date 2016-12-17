---
title: "CDaoParameterInfo-Struktur"
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
  - "CDaoParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoParameterInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Parameters-Auflistung"
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoParameterInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoParameterInfo`\-Struktur enthält Informationen über ein Parameterobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoParameterInfo  
{  
   CString m_strName;       // Primary  
   short m_nType;           // Primary  
   ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Parameterobjekt.  Weitere Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_nType`  
 Ein Wert, der dem Datentyp eines Parameterobjekts angibt.  Eine Liste der möglichen Werte, finden Sie den Member `m_nType` der Struktur unter [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md).  Weitere Informationen finden Sie im Thema "Typeigenschaft" in der DAO\-Hilfe.  
  
 *m\_varValue*  
 Der Wert des Parameters, die in einem Objekt. [COleVariant](../../mfc/reference/colevariant-class.md)  
  
## Hinweise  
 Die Verweise auf primärem und einen sekundären oben genanntem geben an, wie die Informationen durch die [GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)\-Memberfunktion in der `CDaoQueryDef`\- Klasse zurückgegeben werden.  
  
 MFC kapselt nicht DAO\-Parameterobjekte in einer Klasse.  Die DAO\-Querydef\-Objekte, die Objekten MFC\-Klassen `CDaoQueryDef` zugrunde liegen, speichern Parameter in ihren Parameterauflistungen.  Um auf die in [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) zuzugreifen Parameterobjekte \- Objekts, rufen Sie die `GetParameterInfo`\-Memberfunktion des Querydef\-Objekts für einen bestimmten Parameternamen oder einen Index in die Parameterauflistung auf.  Sie können die [CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)\-Memberfunktion in Verbindung mit `GetParameterInfo` verwenden, um sich durch die Parameterauflistung zu durchlaufen.  
  
 Die Informationen, die von der [CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoParameterInfo`\-Struktur gespeichert.  Rufen Sie `GetParameterInfo` für das Querydef\-Objekt auf, in dessen Parameterauflistung das Parameterobjekt gespeichert wird.  
  
> [!NOTE]
>  Wenn Sie den Wert eines Parameters abrufen oder festlegen möchten, verwenden Sie die [GetParamValue](../Topic/CDaoRecordset::GetParamValue.md) und [SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)\-Memberfunktionen der Klasse `CDaoRecordset`.  
  
 `CDaoParameterInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoParameterInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)
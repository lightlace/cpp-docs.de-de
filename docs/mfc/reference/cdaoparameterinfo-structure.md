---
title: CDaoParameterInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b41d26b736ea9f84c53f71dbd71949f74fb8ae52
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 `m_strName`  
 Das Parameterobjekt bezeichnet eindeutig. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 `m_nType`  
 Ein Wert, der den Datentyp eines Parameters-Objekts angibt. Eine Liste der möglichen Werte finden Sie unter der `m_nType` Mitglied der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
 *m_varValue*  
 Der Wert des Parameters, gespeichert einer [COleVariant](../../mfc/reference/colevariant-class.md) Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären und sekundären oben anzugeben, wie die Informationen zurückgegeben werden, durch die [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion Klasse `CDaoQueryDef`.  
  
 MFC ist nicht mit DAO Parameterobjekte in einer Klasse gekapselt. DAO Querydef-Objekte zugrunde liegenden MFC `CDaoQueryDef` Objekte speichern Parameter in ihre Sammlungen Parameter. Zugriff auf die Parameterobjekte in einem [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt, rufen Sie des Querydef-Objekts `GetParameterInfo` Member-Funktion für einen bestimmten Parameternamen oder ein Index in die Parameters-Auflistung. Können Sie die [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) Member-Funktion in Verbindung mit `GetParameterInfo` durchlaufen Sie die Parameters-Auflistung.  
  
 Informationen abgerufen werden, indem Sie die [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) -Memberfunktion befindet sich in einer `CDaoParameterInfo` Struktur. Rufen Sie `GetParameterInfo` für das Querydef-Objekt, das in die Auflistung, deren Parameter den Parameter-Objekt gespeichert ist.  
  
> [!NOTE]
>  Gegebenenfalls zu erhalten oder nur den Wert eines Parameters festzulegen, verwenden Sie die [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) und [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) Memberfunktionen der Klasse `CDaoRecordset`.  
  
 `CDaoParameterInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoParameterInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)


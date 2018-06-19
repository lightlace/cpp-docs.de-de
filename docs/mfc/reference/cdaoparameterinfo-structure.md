---
title: CDaoParameterInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e743e7456c185acd100c898cfb946182d63ce63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366238"
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
 Eindeutig benennt das Parameterobjekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 `m_nType`  
 Ein Wert, der den Datentyp eines Parameters-Objekts angibt. Eine Liste der möglichen Werte finden Sie die `m_nType` Mitglied der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
 *m_varValue*  
 Der Wert des Parameters, gespeichert einer [COleVariant](../../mfc/reference/colevariant-class.md) Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären und sekundären Datenbank, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, durch die [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion in Klasse `CDaoQueryDef`.  
  
 MFC ist DAO-Parameterobjekten in einer Klasse nicht gekapselt werden. Zugrunde liegende MFC-DAO Querydef Objekte `CDaoQueryDef` Parameter im Parameters Auflistungen Speichern von Objekten. Die Parameterobjekte in den Zugriff auf eine [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt, des Querydef-Objekts aufrufen `GetParameterInfo` Memberfunktion für ein bestimmtes Parametername oder einen Index in der Parameterauflistung. Sie können die [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) Memberfunktion in Verbindung mit `GetParameterInfo` so durchlaufen Sie die Parameters-Auflistung.  
  
 Informationen, die abgerufen, indem die [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion befindet sich in einer `CDaoParameterInfo` Struktur. Rufen Sie `GetParameterInfo` für das Querydef-Objekt, das in die Auflistung, deren Parameter das Parameterobjekt gespeichert ist.  
  
> [!NOTE]
>  Zum Abrufen oder legen Sie nur den Wert eines Parameters verwenden Sie ggf. die [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) und [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) Memberfunktionen der Klasse `CDaoRecordset`.  
  
 `CDaoParameterInfo` definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoParameterInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)

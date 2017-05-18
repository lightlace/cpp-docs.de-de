---
title: CDaoErrorInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
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
ms.openlocfilehash: 3a3b33f6a7b95edcb2476b03356d32e74d1b8954
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo-Struktur
Die `CDaoErrorInfo` Struktur enthält Informationen über ein Error-Objekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *m_lErrorCode*  
 Eine numerische DAO-Fehlercode. Finden Sie im Thema "Abfangbarer Datenzugriff" in der DAO-Hilfe.  
  
 *m_strSource*  
 Der Name des Objekts oder der Anwendung, die ursprünglich den Fehler generiert hat. Die Source-Eigenschaft gibt einen Zeichenfolgenausdruck für das Objekt, das ursprünglich den Fehler generiert hat. der Ausdruck ist in der Regel den Namen des Objekts-Klasse. Details finden Sie im Thema "Source-Eigenschaft" in der DAO-Hilfe.  
  
 *m_strDescription*  
 Eine beschreibende Zeichenfolge, die mit einem Fehler verknüpft ist. Details finden Sie im Thema "Description-Eigenschaft" in der DAO-Hilfe.  
  
 *m_strHelpFile*  
 Einen vollqualifizierten Pfad zu einer Microsoft Windows-Hilfedatei. Details finden Sie im Thema "HelpContext HelpFile-Eigenschaften" in der DAO-Hilfe.  
  
 *m_lHelpContext*  
 Eine Kontext-ID für ein Thema in einer Microsoft Windows-Hilfedatei. Details finden Sie im Thema "HelpContext HelpFile-Eigenschaften" in der DAO-Hilfe.  
  
## <a name="remarks"></a>Hinweise  
 MFC ist nicht mit DAO Error-Objekte in einer Klasse gekapselt. Stattdessen die [CDaoException](../../mfc/reference/cdaoexception-class.md) -Klasse stellt eine Schnittstelle für den Zugriff auf die Errors-Auflistung enthalten sind, die über DAO **Datenbankmodul** -Objekt, das Objekt, das auch alle Arbeitsbereiche enthält. Wenn ein MFC-DAO-Vorgang löst eine `CDaoException` Objekt, das Sie abfangen, MFC füllt eine `CDaoErrorInfo` Struktur und speichert sie in des Ausnahmeobjekts [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Member. (Sie DAO direkt aufrufen möchten, rufen Sie des Ausnahmeobjekts [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) Memberfunktion selbst füllen `m_pErrorInfo`.)  
  
 Weitere Informationen zur Behandlung von DAO-Fehlern finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md). Verwandte Informationen finden Sie im Thema "Error-Objekt" in der DAO-Hilfe.  
  
 Informationen abgerufen werden, indem Sie die [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) -Memberfunktion befindet sich in einer `CDaoErrorInfo` Struktur. Untersuchen der [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Datenmember aus einer `CDaoException` -Objekt, das Sie in einem Ausnahmehandler oder Aufruf abfangen `GetErrorInfo` aus einer `CDaoException` -Objekt, das Sie explizit erstellen, um Fehler zu überprüfen, die während eines direkten Aufrufs die DAO-Schnittstellen aufgetreten sind. `CDaoErrorInfo`definiert auch eine `Dump` Memberfunktion im Debugmodus erstellt. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoErrorInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)


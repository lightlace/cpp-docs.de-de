---
title: Klasse CArchiveException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], serialization
- serialization [C++], exceptions
- CArchiveException class
- exceptions [C++], archive
- archive exceptions [C++]
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
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
ms.openlocfilehash: e927bea5b8d9e6dbaafb191f6c3bdcf0f0d076cc
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="carchiveexception-class"></a>CArchiveException-Klasse
Stellt eine serialisierungsausnahmebedingung dar  
  
## <a name="syntax"></a>Syntax  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|Erstellt ein `CArchiveException`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|Gibt die Ursache der Ausnahme.|  
|[CArchiveException::m_strFileName](#m_strfilename)|Gibt den Namen der Datei für diese Ausnahmebedingung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CArchiveException` -Klasse enthält einen öffentlichen Datenmember, der die Ursache der Ausnahme angibt.  
  
 `CArchiveException`-Objekte werden erstellt und ausgelöst in [CArchive](../../mfc/reference/carchive-class.md) Memberfunktionen. Sie können diese Objekte innerhalb des Bereichs zugreifen ein **CATCH** Ausdruck. Der Ursachencode ist unabhängig vom Betriebssystem. Weitere Informationen zur ausnahmeverarbeitung finden Sie unter [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="carchiveexception"></a>CArchiveException::CArchiveException  
 Erstellt eine `CArchiveException` -Objekt, Speichern des Werts `cause` im Objekt.  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `cause`  
 Ein enumerierter Typ-Variable, die den Grund für die Ausnahme angibt. Eine Liste der Enumeratoren finden Sie in der [M_cause](#m_cause) -Datenmember.  
  
 `lpszArchiveName`  
 Verweist auf eine Zeichenfolge mit dem Namen der `CArchive` Objekt, der die Ausnahme verursacht.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CArchiveException` Objekt auf dem Heap und sich selbst auslösen oder lassen Sie die globale Funktion [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) für Sie zu behandeln.  
  
 Verwenden Sie diesen Konstruktor nicht direkt. Rufen Sie stattdessen die globale Funktion `AfxThrowArchiveException`.  
  
##  <a name="m_cause"></a>CArchiveException::m_cause  
 Gibt die Ursache der Ausnahme.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Datenmember ist eine öffentliche Variable des Typs `int`. Die Werte definieren, indem eine `CArchiveException` Enumerationstyps. Die Enumeratoren und ihre Bedeutungen lauten wie folgt:  
  
- **CArchiveException::none** kein Fehler aufgetreten ist.  
  
- **CArchiveException::genericException** nicht angegebener Fehler.  
  
- **CArchiveException::readOnly** versucht, in ein Archiv für das Laden von geöffnet zu schreiben.  
  
- **CArchiveException::endOfFile** Dateiende wurde erreicht, beim Lesen eines Objekts.  
  
- **CArchiveException::writeOnly** versucht, aus einem Archiv, das zum Speichern von geöffnet zu lesen.  
  
- **CArchiveException::badIndex** Ungültiges Dateiformat.  
  
- **CArchiveException::badClass** versucht, ein Objekt in ein Objekt des falschen Typs zu lesen.  
  
- **CArchiveException::badSchema** versucht, ein Objekt mit einer anderen Version der Klasse zu lesen.  
  
    > [!NOTE]
    >  Diese `CArchiveException`-Ursachenenumeratoren unterscheiden sich von den `CFileException`-Ursachenenumeratoren.  
  
    > [!NOTE]
    > **CArchiveException::generic** ist veraltet. Verwendung **GenericException** stattdessen. Wenn **generischen** in einer Anwendung verwendet und erstellt mit/CLR, werden Syntaxfehler, die nicht leicht entschlüsselt werden.  
  
##  <a name="m_strfilename"></a>CArchiveException::m_strFileName  
 Gibt den Namen der Datei für diese Ausnahmebedingung.  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CArchive-Klasse](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)



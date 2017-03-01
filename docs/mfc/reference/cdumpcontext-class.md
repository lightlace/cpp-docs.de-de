---
title: CDumpContext Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDumpContext
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext class
- AfxDump object
- diagnostics, diagnostic classes
- diagnostic classes
- diagnosis, diagnostic classes
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 40d833772735e1079647f8f3205fb8db736843fd
ms.lasthandoff: 02/24/2017

---
# <a name="cdumpcontext-class"></a>CDumpContext-Klasse
Unterstützt die Darstellung gestreamter Diagnoseausgaben als Klartext.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|Erstellt ein `CDumpContext`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|Gibt das angegebene Element im Hexadezimalformat an.|  
|[CDumpContext::Flush](#flush)|Löscht alle Daten im Puffer Dump Kontext.|  
|[CDumpContext::GetDepth](#getdepth)|Ruft eine ganze Zahl, die die Tiefe des Dumps.|  
|[CDumpContext::HexDump](#hexdump)|Gibt die Byte in ein Array im Hexadezimalformat.|  
|[CDumpContext::SetDepth](#setdepth)|Wird die Tiefe des Dumps.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|Fügt der Dumpkontext Variablen und Objekte ein.|  
  
## <a name="remarks"></a>Hinweise  
 `CDumpContext`eine Basisklasse keinen.  
  
 Sie können [AfxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11), ein vordeklariert `CDumpContext` -Objekt, für den Großteil der Ausgabe. Das `afxDump` Objekt ist nur in der Debugversion der Microsoft Foundation Class-Bibliothek verfügbar.  
  
 Mehrere Speicher [Diagnosedienste](../../mfc/reference/diagnostic-services.md) verwenden `afxDump` für ihre Ausgabe.  
  
 Unter Windows-Umgebung, die Ausgabe von vordefinierten `afxDump` Objekt konzeptionell identisch mit der `cerr` streamen, wird an den Debugger über die Windows-Funktion weitergeleitet **OutputDebugString**.  
  
 Die `CDumpContext` -Klasse verfügt über eine überladene Einfügung ( ** << **) Operator für `CObject` Zeiger, die die Daten des Objekts gibt. Wenn Sie eine benutzerdefinierte dumpformat für ein abgeleitetes Objekt benötigen, überschreiben [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Die meisten Microsoft Foundation Classes eine überschriebene Implementierung `Dump` Member-Funktion.  
  
 Nicht von abgeleiteten Klassen `CObject`, wie z. B. `CString`, `CTime`, und `CTimeSpan`, haben ihre eigenen überladene `CDumpContext` Insertion-Operatoren als Strukturen führen häufig verwendet, z. B. **CFileStatus**, `CPoint`, und `CRect`.  
  
 Bei Verwendung der [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) oder [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makro in der Implementierung der Klasse, `CObject::Dump` druckt den Namen Ihrer `CObject`-abgeleiteten Klasse. Andernfalls wird es gedruckt `CObject`.  
  
 Die `CDumpContext` Klasse steht mit Debug und Release-Versionen der Bibliothek, aber die `Dump` Member-Funktion ist nur in der Debugversion definiert. Verwendung **#ifdef _DEBUG**  /  `#endif` Anweisungen, die Ihre Diagnosecode, einschließlich benutzerdefinierter Klammer `Dump` Memberfunktionen.  
  
 Bevor Sie Ihre eigenen erstellen `CDumpContext` -Objekt verwenden, müssen Sie erstellen ein `CFile` Objekt, das als Ziel Dump dient.  
  
 Weitere Informationen zu `CDumpContext`, finden Sie unter [Debuggen MFC-Anwendung](/visualstudio/debugger/mfc-debugging-techniques).  
  
 **#define _DEBUG**  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDumpContext`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="a-namecdumpcontexta--cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpContext::CDumpContext  
 Erstellt ein Objekt der Klasse `CDumpContext`.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf die `CFile` -Objekt, das das Ziel Dump ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `afxDump` -Objekt wird automatisch erstellt.  
  
 Schreiben Sie nicht in der zugrunde liegenden `CFile` während der Dumpkontext aktiv; andernfalls ist, Konflikte mit der Dumpdatei. Unter der Windows-Umgebung wird die Ausgabe an den Debugger über die Windows-Funktion weitergeleitet **OutputDebugString**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#12;](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="a-namedumpashexa--cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::DumpAsHex  
 Gibt den angegebenen Typ, der als Hexadezimalzeichenfolge formatiert.  
  
```  
CDumpContext& DumpAsHex(BYTE b);  
CDumpContext& DumpAsHex(DWORD dw);  
CDumpContext& DumpAsHex(int n);  
CDumpContext& DumpAsHex(LONG l);  
CDumpContext& DumpAsHex(LONGLONG n);  
CDumpContext& DumpAsHex(UINT u);  
CDumpContext& DumpAsHex(ULONGLONG n);  
CDumpContext& DumpAsHex(WORD w);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CDumpContext`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um das Element des angegebenen Typs als Hexadezimalzahl dump. Um ein Array zu speichern, rufen Sie [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#13;](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="a-nameflusha--cdumpcontextflush"></a><a name="flush"></a>CDumpContext::Flush  
 Erzwingt, dass alle Daten im Puffer in die Datei geschrieben werden an der Dumpkontext angefügt ist.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&14;](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="a-namegetdeptha--cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpContext::GetDepth  
 Bestimmt, ob ein Speicherabbild tief oder flach verarbeitet wird.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Tiefe des Dumps als Satz von `SetDepth`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetDepth](#setdepth).  
  
##  <a name="a-namehexdumpa--cdumpcontexthexdump"></a><a name="hexdump"></a>CDumpContext::HexDump  
 Gibt ein Array von Bytes, die als hexadezimale Zahlen formatiert.  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszLine*  
 Eine Zeichenfolge am Anfang einer neuen Zeile ausgegeben.  
  
 *pby*  
 Ein Zeiger auf einen Puffer, der zu sichernden Bytes enthält.  
  
 `nBytes`  
 Die Anzahl der zu sichernden Bytes.  
  
 `nWidth`  
 Maximale Anzahl von Bytes pro Zeile (nicht die Breite der Ausgabezeile) ausgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um ein Abbild ein bestimmten Elementtyps als Hexadezimalzahl [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&#15;](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="a-nameoperatorltlta--cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext::operator&lt;&lt;  
 Gibt die angegebenen Daten in der Dumpkontext.  
  
```  
CDumpContext& operator<<(const CObject* pOb);  
CDumpContext& operator<<(const CObject& ob);  
CDumpContext& operator<<(LPCTSTR lpsz);  
CDumpContext& operator<<(const void* lp);  
CDumpContext& operator<<(BYTE by);  
CDumpContext& operator<<(WORD w);  
CDumpContext& operator<<(DWORD dw);  
CDumpContext& operator<<(int n);  
CDumpContext& operator<<(double d);  
CDumpContext& operator<<(float f);  
CDumpContext& operator<<(LONG l);  
CDumpContext& operator<<(UINT u);  
CDumpContext& operator<<(LPCWSTR lpsz);  
CDumpContext& operator<<(LPCSTR lpsz);  
CDumpContext& operator<<(LONGLONG n);  
CDumpContext& operator<<(ULONGLONG n);  
CDumpContext& operator<<(HWND h);  
CDumpContext& operator<<(HDC h);  
CDumpContext& operator<<(HMENU h);  
CDumpContext& operator<<(HACCEL h);  
CDumpContext& operator<<(HFONT h);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CDumpContext` Verweis. Verwenden den Wert zurückgibt, können Sie in einer einzelnen Zeile des Quellcodes mehrfachem schreiben.  
  
### <a name="remarks"></a>Hinweise  
 Für der Operator zum Einfügen überladen `CObject` Zeiger als auch für die meisten primitiven Typen. Ein Zeiger auf Zeichen führt ein Speicherabbild der Zeichenfolgeninhalt. Ein Zeiger auf `void` führt zu einem hexadezimalen Abbild nur die Adresse. Ein **LONGLONG** führt zu einem Abbild eine 64-Bit-Ganzzahl mit Vorzeichen. Ein **ULONGLONG** führt zu einem Abbild eine 64-Bit-Ganzzahl ohne Vorzeichen.  
  
 Bei Verwendung der `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` Makro in der Implementierung der Klasse, und klicken Sie dann auf den Operator zum Einfügen, durch `CObject::Dump`, druckt den Namen des Ihrer `CObject`-abgeleiteten Klasse. Andernfalls wird es gedruckt `CObject`. Wenn Sie überschreiben die `Dump` Funktion der Klasse, und Sie können eine sinnvolle Ausgabe der Inhalt des Objekts statt eine hexadezimale Abbilddatei bereitstellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities&17;](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="a-namesetdeptha--cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpContext::SetDepth  
 Legt die Tiefe für das Abbild.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Parameter  
 *nNewDepth*  
 Der neue Tiefenwert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen primitiven Typ oder eine einfache Ausgabe werden `CObject` , die keine Verweise auf andere Objekte enthält, dann ist der Wert 0 ist ausreichend. Ein Wert größer als 0 ein Tiefe Dump gibt an, wo alle Objekte gesichert rekursiv. Beispielsweise wird ein Speicherabbild Tiefe einer Auflistung alle Elemente der Auflistung ausgeben. Sie können andere Tiefenwerte bestimmten in den abgeleiteten Klassen verwenden.  
  
> [!NOTE]
>  Zirkelverweise werden umfassende Dumps nicht erkannt und können zu Endlosschleifen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities Nr.&16;](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)


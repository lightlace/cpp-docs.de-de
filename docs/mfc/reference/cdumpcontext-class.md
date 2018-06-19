---
title: CDumpContext Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7acd7e94dbb45439a1812f8572ef442e43f9dab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367392"
---
# <a name="cdumpcontext-class"></a>CDumpContext-Klasse
Unterstützt die Darstellung gestreamter Diagnoseausgaben als Klartext.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|Erstellt ein `CDumpContext`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|Gibt das angegebene Element im Hexadezimalformat an.|  
|[CDumpContext::Flush](#flush)|Leert alle Daten in den Kontextpuffer Dump an.|  
|[CDumpContext::GetDepth](#getdepth)|Ruft eine ganze Zahl, die Tiefe des Speicherabbilds entspricht.|  
|[CDumpContext::HexDump](#hexdump)|Sichert die Bytes in einem Array im hexadezimalen Format enthalten sind.|  
|[CDumpContext::SetDepth](#setdepth)|Legt die Tiefe des Speicherabbilds.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|Fügt der Dumpkontext Variablen und Objekte zu.|  
  
## <a name="remarks"></a>Hinweise  
 `CDumpContext` eine Basisklasse verfügt nicht über.  
  
 Sie können [AfxDump](diagnostic-services.md#afxdump), eine vordeklariert `CDumpContext` Objekt, für die meisten Ihrer Dump-Sicherungen. Die `afxDump` Objekt ist nur in der Debugversion des Microsoft Foundation Class-Bibliothek verfügbar.  
  
 Mehrere des Arbeitsspeichers [Diagnosedienste](../../mfc/reference/diagnostic-services.md) verwenden `afxDump` für ihre Ausgabe.  
  
 Unter der Windows-Umgebung, die Ausgabe der vordefinierten `afxDump` Objekt konzeptionell identisch mit der `cerr` streamen, wird an den Debugger über die Windows-Funktion weitergeleitet **OutputDebugString**.  
  
 Die `CDumpContext` -Klasse verfügt über eine überladene Einfügung ( **<<**) Operator für `CObject` Zeiger, die Daten des Objekts einen Dump erstellt. Wenn Sie eine benutzerdefinierte dumpformat für ein abgeleitetes Objekt benötigen, überschreiben [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Die meisten Microsoft Foundation Classes implementieren eine überschriebene `Dump` Memberfunktion.  
  
 Die nicht von abgeleiteten Klassen `CObject`, wie z. B. `CString`, `CTime`, und `CTimeSpan`, haben ihre eigenen überladene `CDumpContext` Einfügeoperatoren als führen häufig verwendeten Strukturen, z. B. **CFileStatus**, `CPoint`, und `CRect`.  
  
 Bei Verwendung der [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) oder [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) Makros in der Implementierung Ihrer Klasse `CObject::Dump` druckt den Namen des Ihrer `CObject`-abgeleitete Klasse. Wird hingegen Drucken `CObject`.  
  
 Die `CDumpContext` Klasse ist verfügbar, mit der Debugversion und Releaseversion Versionen der Bibliothek, aber die `Dump` Member-Funktion ist nur in der Debugversion definiert. Verwendung **#ifdef _DEBUG**  /  `#endif` Anweisungen, die Ihre Diagnosecode, einschließlich Ihrer benutzerdefinierten Klammer `Dump` Memberfunktionen.  
  
 Bevor Sie Ihre eigenen erstellen `CDumpContext` -Objekt verwenden, müssen Sie erstellen eine `CFile` -Objekt, das als Ziel Dump dient.  
  
 Weitere Informationen zu `CDumpContext`, finden Sie unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques).  
  
 **#define _DEBUG**  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDumpContext`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext  
 Erstellt ein Objekt der Klasse `CDumpContext`.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pFile`  
 Ein Zeiger auf die `CFile` -Objekt, das das Ziel Dump ist.  
  
### <a name="remarks"></a>Hinweise  
 Die `afxDump` -Objekt automatisch erstellt wird.  
  
 Schreiben Sie nicht in den zugrunde liegenden `CFile` während der Dumpkontext aktiv; andernfalls ist, Sie wirkt sich mit der Dumpdatei. Unter der Windows-Umgebung wird die Ausgabe an den Debugger über die Windows-Funktion weitergeleitet **OutputDebugString**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex  
 Den angegebenen Typ, der als Hexadezimalzeichenfolge formatiert ein Abbild sichert.  
  
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
 Rufen Sie diese Memberfunktion, um das Element des angegebenen Typs als eine hexadezimale Zahl zu speichern. Um ein Array zu speichern, rufen [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>  CDumpContext::Flush  
 Erzwingt, dass alle Daten verbleiben in den Puffern an, die in die Datei geschrieben werden an den Dumpkontext angefügt.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>  CDumpContext::GetDepth  
 Bestimmt, ob ein Speicherabbild tief oder flach ausgeführt wird.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Tiefe des Speicherabbilds als Satz von `SetDepth`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetDepth](#setdepth).  
  
##  <a name="hexdump"></a>  CDumpContext::HexDump  
 Ein Array von Bytes, die als hexadezimalen Zahlen formatiert ein Abbild sichert.  
  
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
 Die Anzahl der Bytes, die zu speichern.  
  
 `nWidth`  
 Maximale Anzahl von Bytes pro Zeile (nicht die Stärke der Linie Ausgabe) ausgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Sichern eines bestimmten Elementtyp als eine hexadezimale Zahl [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;  
 Gibt die angegebenen Daten in der Dumpkontext an.  
  
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
 Ein `CDumpContext` Verweis. Verwenden den Rückgabewert, können Sie mehrere einfügungen in einer einzelnen Zeile des Quellcodes schreiben.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator zum Einfügen ist überladen für `CObject` Zeiger ebenso wie für die meisten primitiven Typen. Ein Zeiger auf Zeichen führt ein Speicherabbild der Zeichenfolgeninhalt; Ein Zeiger auf `void` führt zu einer hexadezimalen Dump der Adresse nur. Ein **LONGLONG** führt zu einem Speicherabbild einer 64-Bit-Ganzzahl mit Vorzeichen; Ein **ULONGLONG** führt zu einem Speicherabbild einer 64-Bit-Ganzzahl ohne Vorzeichen.  
  
 Bei Verwendung der `IMPLEMENT_DYNAMIC` oder `IMPLEMENT_SERIAL` Makros in der Implementierung der Klasse, und klicken Sie dann auf den Operator zum Einfügen, über `CObject::Dump`, druckt den Namen des Ihrer `CObject`-abgeleitete Klasse. Wird hingegen Drucken `CObject`. Wenn Sie überschreiben die `Dump` Funktion von der Klasse, und Sie können eine aussagekräftigere Ausgabe der Inhalt des Objekts, statt einen hexadezimalen Dump bereitzustellen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>  CDumpContext::SetDepth  
 Legt die Tiefe für das Speicherabbild fest.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Parameter  
 *nNewDepth*  
 Der neue Tiefenwert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen primitiven Typ oder eine einfache Dump-Sicherungen werden `CObject` , die keine Zeiger auf andere Objekte enthält, und klicken Sie dann der Wert 0 ist ausreichend. Ein Wert größer als 0 einen tiefen Dump gibt an, wo alle Objekte gesichert rekursiv. Beispielsweise wird ein umfassende Dump einer Auflistung alle Elemente der Auflistung sichern. Sie können andere Tiefenwerte für bestimmte in Ihren abgeleiteten Klassen verwenden.  
  
> [!NOTE]
>  Zirkelverweise werden umfassende Dumps nicht erkannt und können zu Endlosschleifen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile-Klasse](../../mfc/reference/cfile-class.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)

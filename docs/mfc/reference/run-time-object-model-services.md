---
title: "Laufzeit-Dienste für Laufzeitobjektmodelle | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8739201489644b0f1695a70d0dc12d04ca47aa68
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-object-model-services"></a>Objektmodelldienste zur Laufzeit
Die Klassen [CObject](../../mfc/reference/cobject-class.md) und [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) mehrere Objektdienste, einschließlich des Zugriffs auf die Laufzeit Klasseninformationen, Serialisierung und die Erstellung von dynamischen Objekts zu kapseln. Alle Klassen abgeleitet `CObject` erben diese Funktionalität.  
  
 Zugriff auf die Laufzeit Klasseninformationen können Sie Informationen über die Klasse eines Objekts zur Laufzeit zu ermitteln. Die Möglichkeit, die Klasse eines Objekts zur Laufzeit zu bestimmen ist nützlich, wenn Sie benötigen zusätzliche Typprüfung Funktionsargumente und wann Sie basierend auf der Klasse eines Objekts von speziellen Code schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.  
  
 Serialisierung ist der Prozess des Schreibens oder Lesen des Objekts Inhalten zu oder aus einer Datei. Serialisierung können Sie um Inhalt des Objekts zu speichern, auch nachdem die Anwendung beendet wird. Das Objekt kann dann aus der Datei gelesen werden, wenn die Anwendung neu gestartet wird. Diese Datenobjekte gelten als "persistente".  
  
 Erstellen eines dynamischen Objekts können Sie ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen. Beispielsweise müssen Dokument anzeigen und Frame-Objekten dynamische Erstellung unterstützt, da das Framework benötigt diese dynamisch erstellen.  
  
 Die folgende Tabelle enthält die MFC-Makros, die die Laufzeit Klasseninformationen, Serialisierung und die dynamische Erstellung unterstützen.  
  
 Weitere Informationen zu diesen Laufzeitobjekt Services und die Serialisierung finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Run-Time-Objektmodelldienste Makros  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|Ermöglicht den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[DECLARE_SERIAL](#declare_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Ermöglicht den Zugriff auf die Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf Laufzeitinformationen (muss in der klassenimplementierung verwendet werden).|  
|[IMPLEMENT_SERIAL](#implement_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|  
|[RUNTIME_CLASS](#runtime_class)|Gibt die `CRuntimeClass` -Struktur, die der benannten Klasse entspricht.|  


 OLE erfordert häufig die dynamische Erstellung von Objekten zur Laufzeit. Beispielsweise muss eine OLE-Server-Anwendung OLE-Elemente dynamisch in Reaktion auf eine Anforderung von einem Client erstellen können. Entsprechend muss ein Automatisierungsserver Elemente in Reaktion auf Anfragen von Benutzeroberflächenautomatisierungs-Clients erstellen können.  
  
 Die Microsoft Foundation Class-Bibliothek bietet zwei bestimmten Makros zu OLE.  
  
### <a name="dynamic-creation-of-ole-objects"></a>Die dynamische Erstellung von OLE-Objekte  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|Ermöglicht es Objekten, die durch OLE-Automatisierung erstellt werden.|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Ermöglicht es Objekten, die OLE-System erstellt werden.|  
  
##  <a name="a-namedeclaredynamica--declaredynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 Fügt die Fähigkeit zur Laufzeit Zugriff auf Informationen über die Klasse eines Objekts beim Ableiten einer Klasse von `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Hinzufügen der `DECLARE_DYNAMIC` Makro mit dem Modul Headerdatei (.h) für die Klasse, fügen Sie dieses Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse.  
  
 Bei Verwendung der **DECLARE**_ **dynamische** und `IMPLEMENT_DYNAMIC` Makros, wie beschrieben, können Sie die `RUNTIME_CLASS` Makro und der `CObject::IsKindOf` Funktion, um die Klasse der Objekte zur Laufzeit zu bestimmen.  
  
 Wenn `DECLARE_DYNAMIC` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNAMIC` muss in der Implementierung der Klasse enthalten sein.  
  
 Weitere Informationen zu den `DECLARE_DYNAMIC` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IMPLEMENT_DYNAMIC](#implement_dynamic).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-namedeclaredyncreatea--declaredyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 Aktiviert die Objekte `CObject`-abgeleitete Klassen dynamisch zur Laufzeit erstellt werden.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Fähigkeit, um neue Objekte dynamisch zu erstellen. Zum Beispiel die neue Ansicht erstellt, wenn Sie ein neues Dokument öffnen. Dokument anzeigen und Frameklassen sollte die dynamische Erstellung unterstützt, da das Framework benötigt diese dynamisch erstellen.  
  
 Hinzufügen der `DECLARE_DYNCREATE` Makro im h-Modul für die Klasse, fügen Sie dieses Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse.  
  
 Wenn `DECLARE_DYNCREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNCREATE` muss in der Implementierung der Klasse enthalten sein.  
  
 Weitere Informationen zu den `DECLARE_DYNCREATE` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  Die `DECLARE_DYNCREATE` Makro enthält alle Funktionen der `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-namedeclareseriala--declareserial"></a><a name="declare_serial"></a>DECLARE_SERIAL  
 Generiert den Code der C++-Header für eine `CObject`-abgeleitete Klasse, die serialisiert werden kann.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Serialisierung ist der Prozess des Schreibens oder Lesen des Inhalts eines Objekts in und aus einer Datei.  
  
 Verwenden der `DECLARE_SERIAL` Makro in eine h-Modul, und fügen Sie dann das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse.  
  
 Wenn `DECLARE_SERIAL` ist in der Klassendeklaration enthalten `IMPLEMENT_SERIAL` muss in der Implementierung der Klasse enthalten sein.  
  
 Die `DECLARE_SERIAL` Makro enthält alle Funktionen der `DECLARE_DYNAMIC` und `DECLARE_DYNCREATE`.  
  
 Können Sie die **AFX_API** Makro automatisch Exportieren der `CArchive` Extraktionsoperator für Klassen verwendet werden, die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Klammer Klassendeklarationen (befindet sich in der h-Datei), durch den folgenden Code:  
  
 [!code-cpp[NVC_MFCCObjectSample&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Weitere Informationen zu den `DECLARE_SERIAL` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&21;](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameimplementdynamica--implementdynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
 Den C++-Code für eine dynamische generiert `CObject`-Klasse zur Laufzeit Zugriff auf den Klassennamen und die Position innerhalb der Hierarchie.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der Name der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `IMPLEMENT_DYNAMIC` Makro in einer CPP-Modul, und ordnen Sie das resultierende Objekt code nur einmal.  
  
 Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&#2;](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&3;](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameimplementdyncreatea--implementdyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 Aktiviert die Objekte `CObject`-abgeleitete Klassen dynamisch zur Laufzeit erstellt werden Zeit, wenn Sie mit der `DECLARE_DYNCREATE` Makro.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der tatsächliche Name der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Fähigkeit zum Erstellen neuer Objekte dynamisch, z. B. wenn ein Objekt während der Serialisierung vom Datenträger gelesen. Hinzufügen der `IMPLEMENT_DYNCREATE` Makro in der Implementierungsdatei der Klasse. Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
 Bei Verwendung der `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` Makros, anschließend können Sie die `RUNTIME_CLASS` Makro und die `CObject::IsKindOf` -Memberfunktion die Klasse der Objekte zur Laufzeit zu bestimmen.  
  
 Wenn `DECLARE_DYNCREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNCREATE` muss in der Implementierung der Klasse enthalten sein.  
  
 Beachten Sie, dass diese Makrodefinition der Standardkonstruktor für die Klasse aufruft. Ein nicht trivialen Konstruktor explizit durch die Klasse implementiert ist, müssen sie auch den Standardkonstruktor auch explizit implementieren. Der Standardkonstruktor der Klasse hinzugefügt werden kann **private** oder **geschützt** Member Abschnitte, um zu verhindern, die von außerhalb der Implementierung der Klasse aufgerufen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&#22;](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&23;](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameimplementseriala--implementserial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL  
 Den C++-Code für eine dynamische generiert `CObject`-Klasse zur Laufzeit Zugriff auf den Klassennamen und die Position innerhalb der Hierarchie.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der Name der Basisklasse.  
  
 *wSchema*  
 Ein **UINT** "Versionsnummer", die im Archiv in ein Programm aktivieren, Deserialisieren zu identifizieren und Behandeln von erstellte Daten codiert werden Programm zuvor Versionen. Die Anzahl der Klasse Schema sein Â €"1.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `IMPLEMENT_SERIAL` Makro in einem Modul .cpp, verknüpfen Sie den resultierenden Code nur einmal.  
  
 Können Sie die **AFX_API** Makro automatisch Exportieren der `CArchive` Extraktionsoperator für Klassen verwendet werden, die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Klammer Klassendeklarationen (befindet sich in der h-Datei), durch den folgenden Code:  
  
 [!code-cpp[NVC_MFCCObjectSample&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Weitere Informationen finden Sie unter der [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&#24;](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="a-nameruntimeclassa--runtimeclass"></a><a name="runtime_class"></a>RUNTIME_CLASS  
 Ruft die Laufzeitklasse-Struktur aus dem Namen einer C++-Klasse.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse (nicht in Anführungszeichen eingeschlossen).  
  
### <a name="remarks"></a>Hinweise  
 `RUNTIME_CLASS`Gibt einen Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Struktur für die durch angegebene Klasse *Class_name*. Nur `CObject`-abgeleitete Klassen, die mit `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, oder `DECLARE_SERIAL` zurück Zeiger auf eine `CRuntimeClass` Struktur.  
  
 Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&#25;](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 
   
##  <a name="a-namedeclareolecreatea--declareolecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE  
 Aktiviert die Objekte `CCmdTarget`-abgeleitete Klassen, die durch OLE-Automatisierung erstellt werden.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Mit diesem Makro können andere OLE-fähige Anwendung Objekte dieses Typs zu erstellen.  
  
 Hinzufügen der `DECLARE_OLECREATE` Makro im h-Modul für die Klasse, und fügen Sie dann das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse.  
  
 Wenn `DECLARE_OLECREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_OLECREATE` muss in der Implementierung der Klasse enthalten sein. Eine Deklaration mithilfe `DECLARE_OLECREATE` müssen auch verwenden `DECLARE_DYNCREATE` oder `DECLARE_SERIAL`.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h  

##  <a name="a-nameimplementolecreatea--implementolecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 Entweder dieses Makro oder [IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d) muss in der Implementierungsdatei für jede Klasse, die verwendet werden `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 *external_name*  
 Der Objektname, der für andere Programme (eingeschlossen in Anführungszeichen) verfügbar gemacht wird.  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 Komponenten von der Klasse **CLSID**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Bei Verwendung von `IMPLEMENT_OLECREATE`, in der Standardeinstellung, die Sie unterstützen nur einzelnen Threadingmodells. Bei Verwendung von `IMPLEMENT_OLECREATE_FLAGS`, Sie können angeben, welche threading-Modell unterstützt das Objekt mit der `nFlags` Parameter.  
  
 Der externe Name ist der Bezeichner für die andere Anwendung verfügbar gemacht. Clientanwendungen verwenden den externen Namen auf ein Objekt dieser Klasse von einem Automatisierungsserver anfordern.  
  
 Die OLE-Klassen-ID ist ein eindeutiger 128-Bit-Bezeichner für das Objekt. Es besteht aus einem **lang**, zwei **WORD**s und acht **BYTE**s, dargestellt durch *l*, *w1*, *w2*, und *b1* über *b8* in der syntaxbeschreibung. Die Assistent und Code-Assistenten erstellen eindeutige OLE-Klassen-IDs für Sie nach Bedarf.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)


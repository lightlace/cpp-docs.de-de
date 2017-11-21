---
title: Exportieren und Importieren mithilfe von AFX_EXT_CLASS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afx_ext_class
dev_langs: C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 753395713bd4831f1dbc55403134898ae68ca182
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exporting-and-importing-using-afxextclass"></a>Exportieren und Importieren mithilfe von AFX_EXT_CLASS  
  
[MFC-Erweiterungs-DLLs](../build/extension-dlls-overview.md) verwenden Sie das Makro **AFX_EXT_CLASS** zum Exportieren von Klassen, die ausführbaren Dateien, die mit der MFC-Erweiterungs-DLL verknüpft das Makro verwenden, um Klassen zu importieren. Mit der **AFX_EXT_CLASS** -Makro, das die gleichen Headerdateien, mit denen die MFC-Erweiterung erstellen DLL mit den ausführbaren Dateien, die mit der DLL verwendet werden kann.  
  
 Fügen Sie in der Headerdatei für die DLL, die **AFX_EXT_CLASS** Schlüsselwort, um die Deklaration der Klasse wie folgt:  
  
```cpp  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
Dieses Makro wird definiert, von MFC als `__declspec(dllexport)` Wenn die Präprozessorsymbole `_AFXDLL` und `_AFXEXT` definiert sind. Aber das Makro wird definiert als `__declspec(dllimport)` Wenn `_AFXDLL` definiert ist und `_AFXEXT` ist nicht definiert. Wenn definiert, das Präprozessorsymbol `_AFXDLL` gibt an, dass die gemeinsam genutzte MFC-Version von der ausführbaren Zieldatei (entweder eine DLL oder eine Anwendung) verwendet wird. Wenn beide `_AFXDLL` und `_AFXEXT` werden definiert, dies bedeutet, dass der ausführbaren Zieldatei eine MFC-Erweiterungs-DLL ist.  
  
Da `AFX_EXT_CLASS` ist definiert als `__declspec(dllexport)` beim Exportieren von einer MFC-Erweiterungs-DLL können Sie ganze Klassen exportieren, ohne die ergänzten Namen für alle von dieser Klasse Symbolen in der DEF-Datei platziert.  
  
Obwohl Sie vermeiden können, erstellen eine DEF-Datei und alle die ergänzten Namen für die Klasse mit dieser Methode ist eine DEF-Datei erstellen effizienter, da die Namen durch Ordnungszahl exportiert werden können. Um die DEF-Datei-Methode für das Exportieren zu verwenden, platzieren Sie den folgenden Code am Anfang und Ende der Headerdatei ein:  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  Gehen Sie beim Exportieren von Inlinefunktionen, sein, da die Möglichkeit, dass Konflikte zwischen Versionen erstellt werden kann. Eine Inlinefunktion ruft in den Code der Anwendung erweitert. Deshalb, wenn Sie die Funktion später neu schreiben, wird er nicht aktualisiert, wenn die Anwendung selbst neu kompiliert wird. DLL-Funktionen können in der Regel wird aktualisiert werden, ohne das Neuerstellen der Anwendungen, die sie verwenden.  
  
## <a name="exporting-individual-members-in-a-class"></a>Exportieren die einzelnen Elemente in einer Klasse  
  
In einigen Fällen empfiehlt es sich um einzelne Member einer Klasse zu exportieren. Angenommen, Sie exportieren eine `CDialog`-abgeleitete Klasse, müssen Sie möglicherweise nur den Konstruktor zu exportieren und die `DoModal` aufrufen. Sie können `AFX_EXT_CLASS` für die einzelnen Elemente, die exportiert werden müssen.  
  
Zum Beispiel:  
  
```cpp  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
Da Sie nicht mehr alle Member der Klasse exportieren, können Sie ein zusätzliches Problem aufgrund der Art und Weise, MFC-Makros Arbeit ausführen. Einige der MFC Hilfsmakros tatsächlich deklarieren oder Datenmember zu definieren. Daher müssen diese Datenmember auch aus einer DLL exportiert werden.  
  
Z. B. die `DECLARE_DYNAMIC` Makro wird wie folgt definiert, wenn Sie eine MFC-Erweiterungs-DLL zu erstellen:  
  
```cpp  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
Die Zeile, die mit statischen beginnt `AFX_DATA` ist kein statisches Objekt innerhalb der Klasse deklarieren. Zum Exportieren diese Klasse ordnungsgemäß, und eine ausführbare Clientdatei die Laufzeitinformationen zugreifen, müssen Sie diese statische Objekt exportieren. Da die statische Objekt mit dem Modifizierer deklariert wird `AFX_DATA`, müssen Sie nur definieren `AFX_DATA` werden `__declspec(dllexport)` beim Erstellen der DLL und definieren ihn als `__declspec(dllimport)` beim Erstellen der ausführbare Client. Da `AFX_EXT_CLASS` ist bereits definiert. auf diese Weise müssen Sie nur redefine `AFX_DATA` identisch sein `AFX_EXT_CLASS` Klassendefinition.  
  
Zum Beispiel:  
  
```cpp  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
  
class CExampleView : public CView  
{  
   DECLARE_DYNAMIC()  
   // ... class definition ...  
};  
  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
MFC verwendet stets die `AFX_DATA` Symbol für Datenelemente, die innerhalb der Makros definiert diese Vorgehensweise funktioniert für alle derartigen Szenarien. Beispielsweise, ob Sie für `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Wenn Sie anstelle von ausgewählten Member der Klasse die gesamte Klasse exportieren, werden statische Datenmember automatisch exportiert.  
  
### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C-Funktionen zur Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Welche Exportmethode ermitteln](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)
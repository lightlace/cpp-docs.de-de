---
title: "Exportieren und Importieren mithilfe von AFX_EXT_CLASS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_ext_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXT_CLASS-Makro"
  - "Ausführbare Dateien [C++], Importieren von Klassen"
  - "Exportieren von Klassen [C++]"
  - "Exportieren von DLLs [C++], AFX_EXT_CLASS-Makro"
  - "Erweiterungs-DLLs [C++], Exportieren von Klassen"
  - "Importieren von DLLs [C++]"
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Exportieren und Importieren mithilfe von AFX_EXT_CLASS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Erweiterungs\-DLLs](../build/extension-dlls-overview.md) verwenden das **AFX\_EXT\_CLASS**\-Makro für den Export von Klassen. Die ausführbaren Dateien, die mit der Erweiterungs\-DLL verknüpft werden, verwenden das Makro, um Klassen zu importieren.  Durch die Verwendung des **AFX\_EXT\_CLASS**\-Makros können die zum Erstellen der Erweiterungs\-DLL verwendeten Headerdateien auch für die ausführbaren Dateien verwendet werden, die mit der DLL verknüpft werden.  
  
 Fügen Sie der Klassendeklaration in der Headerdatei für die DLL das **AFX\_EXT\_CLASS**\-Schlüsselwort wie folgt hinzu:  
  
```  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
 Dieses Makro wird von MFC bei der Definition der Präprozessorsymbole **\_AFXDLL** und `_AFXEXT` als **\_\_declspec\(dllexport\)** definiert.  Wird jedoch **\_AFXDLL** definiert und `_AFXEXT` nicht, wird das Makro als **\_\_declspec\(dllimport\)** definiert.  Wenn das Präprozessorsymbol **\_AFXDLL** definiert ist, gibt es an, dass die gemeinsam genutzte MFC\-Version von der ausführbaren Zieldatei \(entweder eine DLL oder eine Anwendung\) verwendet wird.  Die Definition sowohl von **\_AFXDLL** als auch von `_AFXEXT` deutet darauf hin, dass die ausführbare Zieldatei eine Erweiterungs\-DLL ist.  
  
 Da beim Exportieren aus einer Erweiterungs\-DLL **AFX\_EXT\_CLASS** als **\_\_declspec\(dllexport\)** definiert wird, können Sie ganze Klassen exportieren, ohne dass die ergänzten Namen für alle Symbole der jeweiligen Klasse in der DEF\-Datei enthalten sein müssen.  Diese Methode wird im MFC\-Beispiel [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90) verwendet.  
  
 Obwohl mit dieser Methode das Erstellen einer DEF\-Datei einschließlich aller ergänzten Namen für die Klasse vermieden werden kann, ist die Verwendung einer DEF\-Datei effizienter, da die Namen nach Ordinalzahl exportiert werden können.  Um die DEF\-Dateimethode für den Export zu verwenden, fügen Sie den folgenden Code am Anfang und am Ende der Headerdatei ein:  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  Lassen Sie beim Exportieren von Inlinefunktionen besondere Sorgfalt walten, da hierbei mögliche Versionskonflikte auftreten können.  Eine Inlinefunktion wird als Anwendungscode erweitert. Wenn Sie die Funktion später neu schreiben, wird sie daher nur aktualisiert, wenn die Anwendung selbst neu kompiliert wird.  Normalerweise können DLL\-Funktionen aktualisiert werden, ohne dass die Anwendungen, von denen sie verwendet werden, neu erstellt werden müssen.  
  
## Exportieren von einzelnen Membern einer Klasse  
 In einigen Fällen sollen nur einzelne Member einer Klasse exportiert werden.  Möglicherweise benötigen Sie beim Exportieren einer von `CDialog` abgeleiteten Klasse z. B. nur den Konstruktor und den `DoModal`\-Aufruf.  Sie können **AFX\_EXT\_CLASS** für einzelne Member verwenden, die Sie exportieren müssen.  
  
 Beispiel:  
  
```  
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
  
 Da Sie hier nicht mehr alle Member der Klasse exportieren, kann jedoch aufgrund der Funktionsweise von MFC\-Makros ein zusätzliches Problem auftreten.  Es gibt derzeit verschiedene MFC\-Hilfsmakros, durch die Datenmember deklariert oder definiert werden.  Daher müssen diese Datenmember auch aus der DLL exportiert werden.  
  
 Das `DECLARE_DYNAMIC`\-Makro wird beim Erstellen einer Erweiterungs\-DLL z. B. wie folgt definiert:  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 Durch die Zeile, die mit **static** `AFX_DATA` beginnt, wird ein statisches Objekt innerhalb der Klasse deklariert.  Um diese Klasse korrekt zu exportieren und auf die Laufzeitinformationen eines ausführbaren Clients zuzugreifen, müssen Sie dieses statische Objekt exportieren.  Da das statische Objekt mit dem `AFX_DATA`\-Modifizierer deklariert wird, müssen Sie `AFX_DATA` beim Erstellen der DLL einfach als **\_\_declspec\(dllexport\)** und beim Erstellen des ausführbaren Clients als **\_\_declspec\(dllimport\)** definieren.  Da **AFX\_EXT\_CLASS** bereits auf diese Art definiert ist, müssen Sie lediglich eine Neudefinition vornehmen, sodass `AFX_DATA` im Kontext der Klassendefinition **AFX\_EXT\_CLASS** entspricht.  
  
 Beispiel:  
  
```  
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
  
 MFC verwendet stets das `AFX_DATA`\-Symbol für Datenelemente, die innerhalb der Makros definiert werden. Daher wird diese Methode in allen derartigen Szenarios unterstützt.  So ist sie beispielsweise auch auf `DECLARE_MESSAGE_MAP` anwendbar.  
  
> [!NOTE]
>  Wenn Sie anstelle ausgewählter Klassenmember die gesamte Klasse exportieren, werden statische Datenmember automatisch exportiert.  
  
### Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)
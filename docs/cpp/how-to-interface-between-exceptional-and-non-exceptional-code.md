---
title: "Gewusst wie: Verbinden von Code, der Ausnahmen zul&#228;sst, mit Code ohne Ausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Gewusst wie: Verbinden von Code, der Ausnahmen zul&#228;sst, mit Code ohne Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie die konsistente Ausnahmebehandlung in einem C\+\+\-Modul implementiert wird und wie diese Ausnahmen zu und von Fehlercodes an den Ausnahmegrenzen übertragen werden.  
  
 Manchmal muss ein C\+\+\-Modul eine Verbindung mit Code herstellen, der keine Ausnahmen verwendet \(Nicht\-Ausnahmecode\).  Eine solche Schnittstelle wird als *Ausnahmegrenze* bezeichnet.  Sie können z. B. die Win32\-Funktion `CreateFile` im C\+\+\-Programm aufrufen.  `CreateFile` löst keine Ausnahmen aus. Stattdessen werden Fehlercodes festgelegt, die von der `GetLastError`\-Funktion abgerufen werden können.  Wenn das C\+\+\-Programm wichtig ist, möchten Sie vielleicht über eine konsistente ausnahmenbasierte Fehlerbehandlungsrichtlinie für das Programm verfügen.  Und Sie möchten wahrscheinlich keine Ausnahmen verwerfen, nur weil Sie über eine Verbindung mit Nicht\-Ausnahmencode verfügen. Ebenso wenig möchten Sie auf Ausnahmen basierende und nicht auf Ausnahmen basierende Fehlerrichtlinien im C\+\+\-Modul kombinieren.  
  
## Aufrufen von Nicht\-Ausnahmefunktionen von C\+\+  
 Wenn Sie eine Nicht\-Ausnahmefunktion von C\+\+ aufrufen, kann diese Funktion in einer C\+\+\-Funktion umschlossen werden, die alle Fehler erkennt und dann möglicherweise eine Ausnahme auslöst.  Beim Entwerfen einer solchen Wrapperfunktion legen Sie zuerst fest, welche Art von Ausnahmegarantie bereitgestellt wird: die starke Garantie, die grundlegende Garantie oder die Nothrow\-Garantie.  Als nächstes entwerfen Sie die Funktion so, dass alle Ressourcen, z. B. Dateihandles, ordnungsgemäß freigegeben werden, wenn eine Ausnahme ausgelöst wird.  In der Regel bedeutet dies, dass Sie intelligente Zeiger oder ähnliche Ressourcen\-Manager zum Erwerben der Ressourcen verwenden.  Weitere Informationen zu Designüberlegungen finden Sie unter [Gewusst wie: Entwurfsrichtlinien für sichere Ausnahmebehandlung](../cpp/how-to-design-for-exception-safety.md).  
  
### Beispiel  
 Das folgende Beispiel zeigt C\+\+\-Funktionen, die die Win32\-Funktionen `CreateFile` und `ReadFile` intern verwenden, um zwei Dateien zu öffnen und zu lesen.  Die `File`\-Klasse ist ein RAII\-Wrapper \(Resource Acquisition Is Initialization\) für die Dateihandles.  Sein Konstruktor erkennt den Zustand "Datei nicht gefunden" und löst eine Ausnahme aus, um den Fehler in der Aufrufliste des C\+\+\-Moduls weiterzugeben \(in diesem Beispiel die `main()`\-Funktion.\)  Wenn eine Ausnahme ausgelöst wird, nachdem ein `File`\-Objekt vollständig erstellt wurde, ruft der Destruktor automatisch `CloseHandle` auf, um das Dateihandle freizugeben. \(Bei Bedarf können Sie auch die `CHandle`\-Klasse in ATL \(Active Template Library\) zu diesem Zweck verwenden, oder `unique_ptr` mit einem benutzerdefinierten Deleter.\) Die Funktionen, die Win32\- und CRT\-APIs aufrufen, erkennen Fehler und lösen dann mithilfe der lokal definierten `ThrowLastErrorIf`\-Funktion C\+\+\-Ausnahmen aus, welche wiederum die `Win32Exception`\-Klasse verwendet, die von der `runtime_error`\-Klasse abgeleitet wird.  Alle Funktionen in diesem Beispiel stellen eine starke Ausnahmegarantie bereit. Wenn an irgendeinem Punkt in diesen Funktionen eine Ausnahme ausgelöst wird, kommt es nicht zum Verlust von Ressourcen und es wird keine Programmzustand geändert.  
  
```cpp  
// compile with: /EHsc  
#include <Windows.h>  
#include <stdlib.h>  
#include <vector>  
#include <iostream>  
#include <string>  
#include <limits>  
#include <stdexcept>  
  
using namespace std;  
  
string FormatErrorMessage(DWORD error, const string& msg)  
{  
    static const int BUFFERLENGTH = 1024;  
    vector<char> buf(BUFFERLENGTH);  
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),   
        BUFFERLENGTH - 1, 0);   
    return string(buf.data()) + "   ("  + msg  + ")";  
}  
  
class Win32Exception : public runtime_error  
{      
private:  
    DWORD m_error;  
public:  
    Win32Exception(DWORD error, const string& msg)  
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }  
  
    DWORD GetErrorCode() const { return m_error; }  
};  
  
void ThrowLastErrorIf(bool expression, const string& msg)   
{   
    if (expression) {   
        throw Win32Exception(GetLastError(), msg);   
    }   
}   
  
class File  
{  
private:  
    HANDLE m_handle;  
  
    // Declared but not defined, to avoid double closing.  
    File& operator=(const File&);  
    File(const File&);  
public:  
    explicit File(const string& filename)   
    {  
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,   
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);  
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,   
            "CreateFile call failed on file named " + filename);  
    }  
  
    ~File() { CloseHandle(m_handle); }  
  
    HANDLE GetHandle() { return m_handle; }  
};  
  
size_t GetFileSizeSafe(const string& filename)  
{  
    File fobj(filename);  
    LARGE_INTEGER filesize;  
  
    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);  
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);  
  
    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {  
        return filesize.QuadPart;  
    } else {  
        throw;   
    }  
}  
  
vector<char> ReadFileVector(const string& filename)  
{  
    File fobj(filename);  
    size_t filesize = GetFileSizeSafe(filename);  
    DWORD bytesRead = 0;  
  
    vector<char> readbuffer(filesize);  
  
    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),   
        &bytesRead, nullptr);  
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);  
  
    cout << filename << " file size: " << filesize << ", bytesRead: "   
        << bytesRead << endl;  
  
    return readbuffer;  
}  
  
bool IsFileDiff(const string& filename1, const string& filename2)   
{  
    return ReadFileVector(filename1) != ReadFileVector(filename2);  
}   
  
#include <iomanip>  
  
int main ( int argc, char* argv[] )  
{  
    string filename1("file1.txt");  
    string filename2("file2.txt");  
  
    try  
    {  
        if(argc > 2) {  
            filename1 = argv[1];  
            filename2 = argv[2];  
        }   
  
        cout << "Using file names " << filename1 << " and " << filename2 << endl;  
  
        if (IsFileDiff(filename1, filename2)) {  
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
        }  
    }  
    catch(const Win32Exception& e)  
    {          
        ios state(nullptr);  
        state.copyfmt(cout);  
        cout << e.what() << endl;  
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')   
            << e.GetErrorCode() << endl;  
        cout.copyfmt(state); // restore previous formatting  
    }  
}  
  
```  
  
## Aufrufen von Ausnahmecode von Nicht\-Ausnahmecode aus  
 C\+\+\-Funktionen, die als "extern C" deklariert sind, können von C\-Programmen aufgerufen werden.  C\+\+\-COM\-Server können von Code genutzt werden, der in einer von mehreren verschiedenen Sprachen geschrieben wurde.  Wenn Sie öffentliche ausnahmenbasierte Funktionen in C\+\+ implementieren, die von Nicht\-Ausnahmecode aufgerufen werden sollen, darf die C\+\+\-Funktion nicht zulassen, dass Ausnahmen wieder an den Aufrufer übergeben werden.  Daher muss die C\+\+\-Funktion jede Ausnahme explizit abfangen, die sie behandeln kann, und die Ausnahme ggf. in einen Fehlercode konvertieren, den der Aufrufer versteht.  Wenn nicht alle möglichen Ausnahmen bekannt sind, sollte die C\+\+\-Funktionen über einen `catch(…)`\-Block als letzten Handler verfügen.  In diesem Fall empfiehlt es sich, dem Aufrufer einen schwerwiegenden Fehler zu melden, da das Programm sich in einem unbekannten Zustand befinden könnte.  
  
 Das folgende Beispiel zeigt eine Funktion, die voraussetzt, dass es sich bei jeder möglicherweise ausgelösten Ausnahme entweder um den Typ "Win32Exception" handelt oder um einen Ausnahmetyp, der von `std::exception` abgeleitet wird.  Die Funktion fängt jede Ausnahme dieser Typen ab und gibt die Fehlerinformationen als Win32\-Fehlercode an den Aufrufer weiter.  
  
```cpp  
BOOL DiffFiles2(const string& file1, const string& file2)   
{   
    try   
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return FALSE;   
        }   
        return TRUE;   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }  
  
    catch(std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return FALSE;   
}  
  
```  
  
 Bei Konvertierungen von Ausnahmen in Fehlercodes besteht ein mögliches Problem darin, dass Fehlercodes häufig nicht die umfangreichen Informationen enthalten, die eine Ausnahme speichern kann.  Um dieses Problem zu beheben, können Sie einen `catch`\-Block für jeden einzelnen Ausnahmetyp bereitstellen, der ausgelöst werden kann, und durch Protokollierung die Details der Ausnahme erfassen, bevor sie in einen Fehlercode konvertiert wird.  Durch diesen Ansatz können viele Codewiederholungen erstellt werden, wenn mehrere Funktionen denselben Satz von `catch`\-Blöcken verwenden.  Eine gute Möglichkeit zur Vermeidung von Codewiederholungen besteht in der Umgestaltung dieser Blöcke in eine private Hilfsfunktion, die die Blöcke `try` und `catch` implementiert und ein Funktionsobjekt akzeptiert, das im `try`\-Block aufgerufen wird.  Übergeben Sie den Code in jeder öffentlichen Funktion als Lambda\-Ausdruck an die Hilfsfunktion.  
  
```cpp  
template<typename Func>   
bool Win32ExceptionBoundary(Func&& f)   
{   
    try   
    {   
        return f();   
    }   
    catch(Win32Exception& e)   
    {   
        SetLastError(e.GetErrorCode());   
    }   
    catch(const std::exception& e)   
    {   
        SetLastError(MY_APPLICATION_GENERAL_ERROR);   
    }   
    return false;   
}  
  
```  
  
 Das folgende Beispiel zeigt, wie der Lambda\-Ausdruck geschrieben wird, der das Funktionselement definiert.  Wenn ein Funktionselement "inline" mithilfe eines lambda\-Ausdrucks definiert wird, ist es oft besser lesbar, als wenn es als benanntes Funktionsobjekt geschrieben worden wäre.  
  
```cpp  
bool DiffFiles3(const string& file1, const string& file2)   
{   
    return Win32ExceptionBoundary([&]() -> bool  
    {   
        File f1(file1);   
        File f2(file2);   
        if (IsTextFileDiff(f1, f2))   
        {   
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);   
            return false;   
        }   
        return true;   
    });   
}  
  
```  
  
 Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  
  
## Siehe auch  
 [Behandeln von Fehlern und Ausnahmen](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Gewusst wie: Entwurfsrichtlinien für sichere Ausnahmebehandlung](../cpp/how-to-design-for-exception-safety.md)
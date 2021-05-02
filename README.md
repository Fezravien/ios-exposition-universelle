# Exposition Universelle 🇰🇷 

### 파리 만국박람회 🇬🇧 - 한국 출품작 🇰🇷

### 🗓 21.04.05 ~ 21.04.21

### 👥 개인

---

### Index

- [Simulator](#Simulator)
- [구현 및 기능](#구현 및 기능)
- [설계](#설계 및 구현)
- [Trouble Shooting](#Trouble Shooting)
- [학습한 내용](#학습한 내용)

<br/>

---

## Simulator

<img src="https://user-images.githubusercontent.com/44525561/116815883-9bac3680-ab9a-11eb-84a5-de92fbdc0ea9.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01 00 02" style="zoom:67%;" /> <img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3dbfhbdkg30880hsqv8.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 00.33.00" style="zoom:67%;" />

<br/>

---

## 구현 및 기능

- [Page 1 - 메인](#메인 페이지)
- [Page 2 - 한국의 출품작](#한국의 출품작 페이지)
- [Page 3 - 한국의 출품작 세부내용](#출품작 상세내용 페이지)
- [오토레이아웃](#오토레이아웃)

<br/>

### 메인 페이지

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3dd9huitg30880hs7wj.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01.00.02" style="zoom:75%;" /> 

- 상하 스크롤을 이용해 파리 만국박람회 1900의 `방문객`, `개최지`, `개최 기간`, `내용`을 확인 할 수 있다.
- 최하단에 `한국 출풀작 보러가기` 버튼으로 두 번째 페이지인 한국의 출품작으로 이동할 수 있다.
- 화면 모드 - portrait

<br/>

### 한국의 출품작 페이지

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3dfq34ewg30880hsb29.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01.02.33" style="zoom:75%;" /> <img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3ervb563g30880hshdt.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01.48.25" style="zoom:75%;" />

- 상하 스크롤을 이용해 한국의 출품작 목록을 확인할 수 있다.
- 각각의 출품작에는 `이미지`, `제목`, `요약된 내용`을 확인할 수 있다.
- 화면 모드 - all

<br/>

### 출품작 상세내용 페이지

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3eseq2xhg30880hskjl.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01.48.41" style="zoom:75%;" /> <img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq3etaebe6g30880hskjl.gif" alt="Simulator Screen Recording - iPhone 12 Pro - 2021-05-02 at 01.50.08" style="zoom:75%;" />

- 상하 스크롤을 이용해 한국의 출품작 상세내용 페이지의 제목, 이미지, 내용을 확인할 수 있다.
- 화면 모드 - all

<br/>

### 오토레이아웃

- 모든 아이폰 기기에 맞게 오토레이아웃 적용 
- Dynamic Type 적용

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq4fun7srfj30u01sxduj.jpg" alt="Simulator Screen Shot - iPhone 12 Pro - 2021-05-02 at 00.34.59" style="zoom:20%;" /> <img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq4fupzfq4j31720hwq4a.jpg" alt="스크린샷 2021-05-02 오전 12.35.58" style="zoom:35%;" />



<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq4fuvre9wj30u01sxgx5.jpg" alt="Simulator Screen Shot - iPhone 12 Pro - 2021-05-02 at 00.35.40" style="zoom:20%;" /> <img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq4fv0fp14j31720hw75m.jpg" alt="스크린샷 2021-05-02 오전 12.37.01" style="zoom:35%;" /> 

<br/>

---

## 설계

- [UML](#UML)
- [파일 구조](#파일 구조)

<br/>

### UML

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq42h135nbj31mn0u0gyq.jpg" alt="만국기 UML" style="zoom:100%;" /> 

<br/>

### 파일 구조

- MVC

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gq46mswmw7j30wc0u0wio.jpg" alt="만국기 파일구조" style="zoom:50%;" /> 

<br/>

#### Model

- `Expo` : [Page 1] 메인 페이지 데이터 구조 - Codable
- `StateEntry` : [Page 2] 한국의 출품작 데이터 구조 - Codable
- `DecodeData` : JSON 파일 파싱하기 위한 POP - NSDataAsset, JSONDecoder

<br/>

#### ViewController

- Cell
  - `KoreaEntryTableViewCell` : [Page 2] 데이블의 셀을 커스터마이징 - xib 
- Entry
  - Korea
    - `KoreaEntryViewController` : [Page 2] 테이블 뷰(dataSource, delegate) -xib 
    - `KoreaEntryDetailViewController ` : [Page 3] 출품작 상세 내용 - xib
- ExpoViewController : [Page 1] 메인 페이지 구성 

<br/>

#### Utilities

- extension
  - `Alter` : UIViewController를 extension 하여 alter를 범용적으로 사용하게 구현
  - `Navieation` : UINavigationController를 extension 하여 화면 전환을 각각의 뷰에서 가능하도록 구현
- Error
  - `ExpoError` : 열거형에 오류 프로토콜을 채택하여 오류 처리를 구현

 <br/>

---

## Trouble Shooting

### JSON 파싱을 위한 모델 구현

#### Trouble

- JSON 파싱을 위한 모델의 타입에 맞지 않거나, 틀린 형식이 들어오면 어떻게 처리하지?
- 오류처리 하는 방식을 모델에서 처리할지, 뷰 컨트롤러에서 파싱을 호출할때 처리할지 

<br/>

#### TroubleShooting

```swift
// [Page 2] 한국의 출품작 데이터 모델 
struct StateEntry: Decodable {
    let name: String
    let imageName: String
    let shortDescription: String
    let description: String
    
    private enum CodingKeys: String, CodingKey {
        case name
        case imageName = "image_name"
        case shortDescription = "short_desc"
        case description = "desc"
    }
    
    init(from decoder: Decoder) throws {
        let container = try decoder.container(keyedBy: CodingKeys.self)
        self.name = (try? container.decode(String.self, forKey: .name)) ?? ""
        self.imageName = (try? container.decode(String.self, forKey: .imageName)) ?? ""
        self.shortDescription = (try? container.decode(String.self, forKey: .shortDescription)) ?? ""
        self.description = (try? container.decode(String.self, forKey: .description)) ?? ""
    }
}
```

모델에서 오류처리를 하여 뷰 컨트롤러에서 하는 작업을 줄이는 것을 목표로 했다. 

JSON 파싱을 위한 모델에 맞지 않는 구조가 들어왔을때 `이니셜라이저` 에서  `Nil 병합 연산자`로 빈 문자열을 반환 하도록 처리하는 방식으로 구현했다.

이렇게 처리함으로써 오류에 의해 앱이 강제 종료되는 상황을 막아 가용성을 높일 수 있다고 생각했고, 뷰 컨트롤러의 작업을 줄일 수 있었다.

<br/>
---![image](https://user-images.githubusercontent.com/44525561/116816312-69033d80-ab9c-11eb-8eb4-374f11c46e3d.gif)

<br/>

### 1 : M 화면전환으로 확장성 넓히기 

A 화면에서 B 화면으로 데이터를 전달하고 화면 이동이 이뤄질 때 (현재 프로젝트 - Navigation push/pop 방식, Xib)

- [Page 2] 한국의 출품작 테이블의 셀을 눌렀을때 
  - A 화면에서 B 화면 객체 생성
  - 생성된 B 화면 객체에 데이터 삽입
  - B 객체를 `pushViewController()`로 push 하여 화면전환

```swift
// A (KoreaEntryViewController)
func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
		let koreaDetailEntryViewController = KoreaDetailEntryViewController()
		koreaDetailEntryViewController.detailEntry = self.koreaEntrys[indexPath.row]
		self.navigationController?.pushViewController(koreaDetailEntryViewController, animated: true)
}

// B (KoreaDetailEntryViewController)
private var detailEntry: StateEntry?
```

<br/>

#### Trouble

A -> B 인 경우가 현재 요구사항이지만, C -> B 인 요구사항이 있을경우 대비되지 않아 데이터를 빼먹을 수 있다.

예를 들어, "사용자 정보" 같은 화면에 대한 요구사항이 있을 경우 어디서든지 "사용자 정보" 페이지로 넘어갈 수 있다.

<br/>

#### TroubleShooting

```swift
// A (KoreaEntryViewController)
func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
		self.navigationController?.pushViewController
  		(KoreaDetailEntryViewController.initDetailEntryData(koreaEntrys[indexPath.row]), animated: true)
}

// B (KoreaDetailEntryViewController)
private var detailEntry: StateEntry?

static func initDetailEntryData(_ data: StateEntry) -> KoreaDetailEntryViewController {
      let viewController = KoreaDetailEntryViewController(nibName: nil, bundle: nil)
      viewController.detailEntry = data
      return viewController
}

```

`static 메소드`를 통해서 B 화면 객체를 생성할때 데이터를 넣어주도록 강제하므로 데이터가 없어서 빈 화면을 띄워줄 수 있는 여지를 감소시켰다.

이런 상황은 어떠한 곳에서도 바로 띄워줄 필요가 있는 화면에서는 특히 더 필요한 처리인 것 같다!

<br/>
---
<br/>

### AppDelegate 접근문제 - 화면 모드, 데이터 저장

###### 화면 모드 

- [Page 1] 메인 페이지 - `protrait`
- [Page 2] 한국의 출품작 - `all`
- [Page 3] 출품작 상세 페이지 - `all`

##### JSON 파싱 데이터 저장

- 화면이 생성될 때마다 JSON 파싱을 진행하므로 AppDelegate에서 관리하도록 함

<br/>

#### Trouble

각각의 뷰 컨트롤러 마다 아래 코드로 싱글톤인 AppDelegate을 사용했다.

```swift
// other View 
private var appDelegate = UIApplication.shared.delegate as? AppDelegate

// AppDelegate
var shouldSupportAllOrientation = true
var koreaEntrys: [StateEntry] = []
var detailEntry: StateEntry?
var expoData: Expo?
    
func application(_ application: UIApplication, 
                 supportedInterfaceOrientationsFor window: UIWindow?) -> UIInterfaceOrientationMask {
    if shouldSupportAllOrientation == true {
        return UIInterfaceOrientationMask.all
    } else {
        return UIInterfaceOrientationMask.portrait
    }
}
```

- `AppDelegate`는 앱의 전체 라이프 사이클에 해당하는 기능을 담당한다.
- 상위 방향으로 참조를 가지는 것은 순환 참조 관계가 발생할 수 있다. (weak, strong)

<br/>

#### ThroubleShooting

##### 화면 전환

```swift
// UINavigationController Extension
extension UINavigationController {
    override open var shouldAutorotate: Bool {
        get {
            if let visibleVC = visibleViewController {
                return visibleVC.shouldAutorotate
            }
            return super.shouldAutorotate
        }
    }
    
    override open var supportedInterfaceOrientations: UIInterfaceOrientationMask {
        get {
            if let visibleVC = visibleViewController {
                return visibleVC.supportedInterfaceOrientations
            }
            return super.supportedInterfaceOrientations
        }
    }
}

// [Page 1] 메인 페이지 
override var shouldAutorotate: Bool {
        return false
}
    
override var supportedInterfaceOrientations: UIInterfaceOrientationMask {
        return [.portrait]
}

override func viewWillAppear(_ animated: Bool) {
      super.viewWillAppear(animated)

      let orientaion = UIDeviceOrientation.portrait.rawValue
      UIDevice.current.setValue(orientaion, forKey: "orientation")
        
      self.navigationController?.navigationBar.isHidden = true
}

```

`NavigationController` 을 `extension`으로 각각의 뷰 컨트롤러에서 동작할 수 있도록 기존의 `AppDelegate` 접근 하는 방식에서 수정했다.

```swift
// 화면이 자동으로 변화되는 것 설정
shouldAutorotate

// 허용하는 화면 모드 설정
supportedInterfaceOrientations

// 강제로 디바이스의 화면 모드를 정해주기 
override func viewWillAppear(_ animated: Bool) {
		let orientaion = UIDeviceOrientation.portrait.rawValue
		UIDevice.current.setValue(orientaion, forKey: "orientation")
}
```

[Page 1] 메인 페이지의 화면은 세로 고정이므로 `shouldAutorotate`값을 false로 하여 고정하고, 허용 모드를 `portrait`으로 설정했다.

또한, viewWillAppear 을 통해 메인 페이지에 올때 무조건 `portrait` 으로 강제하도록 지정했다.

<br/>

##### 데이터 저장

데이터 저장을 여기서 시도한 이유는 화면이 생성될 때 마다 지속적으로 JSON 파싱을 수행하는 것이 비효율적이지 않을까 생각했었다. 하지만 좀더 넓게 생각했을때 만약 중간에 데이터의 변경이 존재한다면 업데이트에 문제가 발생할 것이다. 또한, 화면의 모든 데이터를 메모리에 계속 가지고 있게 되고 이러한 측면에서 클아이언트의 데이터 보다는 서버의 DB가 상대적으로 신뢰도가 높으므로 각각의 뷰 컨트롤러에서 생성하고 소멸하도록 수정했다.

<br/>
---

<br/>

### JSON 파싱하기 

- [Page 1] 메인 페이지 - `exposition_universelle_1900.json` 파싱
- [Page 2] 한국의 출품작 - `item.json` 파싱 

<br/>

#### Trouble

파싱이라는 작업이 각각의 뷰 마다 공통적으로 동작해서 개선의 필요성이 있었다. 

<br/>

#### ThroubleShooting

##### pop 활용하기 

```swift
protocol JsonDecoding {
    func jsonDecode<T>(assetName: String) throws -> Result<T, ExpoError> where T: Decodable
}

extension JsonDecoding {
    func jsonDecode<T>(assetName: String) throws -> Result<T, ExpoError> where T: Decodable {
        guard let dataAsset = NSDataAsset(name: assetName) else {
            return .failure(ExpoError.expoData)
        }
        return .success(try JSONDecoder().decode(T.self, from: dataAsset.data))
    }
}
```

class / struct 를 만들어서 json 파싱을 하는 객체를 만드는 것 보다 `protocol, extension, generic` 을 활용해서 활용성을 더 높혔다. 

<br/>

<br/>

---

## 학습한 내용 

- Codable을 채택하여 JSON 데이터와 매칭할 모델 타입 구현
- 스네이크 케이스 또는 축약형인 JSON 키 값을 스위프트의 네이밍에 맞게 변환
- 테이블뷰의 Delegate와 Data Source의 역할의 이해
- 테이블뷰의 셀의 재사용 이해
- 테이블뷰의 전반적인 동작 방식의 이해
- 주어진 JSON 데이터를 파싱하여 테이블뷰에 표시
- 내비게이션 컨트롤러를 활용한 화면 전환
- 뷰 컨트롤러 사이의 데이터 전달
- 오토 레이아웃을 적용하여 다양한 기기에 대응
- Word Wrapping / Line Wrapping / Line Break 방식의 이해
- 접근성(Accessibility)의 개념과 필요성 이해
- Dynamic Types를 통해 텍스트 접근성 향상


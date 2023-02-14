# 프로젝트 설명
+ AVPlayerViewController를 사용하면 앱 내부에 저장되어 있는 비디오 파일뿐만 아니라 외부에 링크된 비디오 파일도 간단하게 재생이 가능합니다. 비디오 재생 앱을 만들어 봅시다.
---

# 전체 소스 & 해석
+ ViewController.swift
```swift

import UIKit
import AVKit // 헤더 파일 추가 

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }
    @IBAction func btnPlayInternalMovie(_ sender: UIButton) {
    // 내부 파일 mp4
        let filePath:String? = Bundle.main.path(forResource: "FastTyping", ofType: "mp4") // 비디오 파일명을 사용하여 비디오가 저장된 앱 내부의 파일 경로 받아오기 
        let url = NSURL(fileURLWithPath: filePath!) // NSURL 형식으로 변경 
        
        playVideo(url: url) // 앞에서 얻은 url로 비디오 재생
        
 /*     let playerController = AVPlayerViewController() 
        let player = AVPlayer(url: url as URL)  
        playerController.player = player
        
        self.present(playerController, animated: true){
            player.play()    */
         
         }
        
    }
    @IBAction func btnPlayExternalMovie(_ sender: UIButton) {
    // 외부 파일 mp4
        let url = NSURL(string: "https://dl.dropboxusercontent.com/s/e38auz050w2mvud/Fireworks.mp4")! // 외부 링크 주소를 NSURL 형식으로 변경
        
        playVideo(url: url)
        
   /*   let playerController = AVPlayerViewController()
        let player = AVPlayer(url: url as URL)
        playerController.player = player
        
        self.present(playerController,animated: true){
            player.play()   /*
     } 
        }
    
    private func playVideo(url: NSURL){
        let playerController = AVPlayerViewController()  // AVPlayerViewController의 인스턴스 생성 
        let player = AVPlayer(url: url as URL)  // 비디오 url로 초기화된 AVPlayer 인스턴스 생성 
        playerController.player = player  // AVPlayer 인스턴스를 할당 
        
        self.present(playerController,animated: true){
            player.play() // 비디오 재생 
        }
    }
}

```
---
# 스크린샷
![image](https://user-images.githubusercontent.com/106370789/173612415-2956e17b-9988-48b6-b594-6d5a9cae563b.png)

![image](https://user-images.githubusercontent.com/106370789/173612492-5b41d313-3605-45e6-aa49-fa596ded472d.png)

![image](https://user-images.githubusercontent.com/106370789/173612550-c740d402-5ed5-4121-bb05-3ad1bd085735.png)

---
# 출처
스위프트로 아이폰 앱 만들기 입문 개정 6판





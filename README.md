# 顔検出を行い、検出した顔にぼかしの処理を施すアプリ

このアプリは、iOSデバイスのカメラを使用して顔検出を行い、検出した顔にブラー処理を適用します。

## 機能

- カメラを使用して顔検出を行う
- 検出した顔にブラー処理を適用する
- ブラー処理の適用条件は、顔の向きと時間経過に基づいて決定される
- 処理は、顔が正面を向いているときは適用されない。また、正面を向いてから1.5秒間はブラー処理を停止している。

## 実装

- `FaceViewController` クラスは、`AVCaptureVideoDataOutputSampleBufferDelegate` プロトコルに準拠して、カメラの映像を取得し、顔検出を行う。
- `detectFaces(on:)` メソッドは、`VNDetectFaceLandmarksRequest` を使用して顔検出を行い、検出した顔にブラー処理を適用する。
- `shouldApplyBlur(_:)` メソッドは、ブラー処理の適用条件を判定する。

## 依存関係

- `UIKit` フレームワーク
- `AVFoundation` フレームワーク
- `Vision` フレームワーク

## 参考

- 【Swift】Vision.frameworkでカメラ画像の顔認識を行う【iOS】(https://qiita.com/beckyJPN/items/4bc46a8e6a000b711de6)
- [[iOS 11] 画像解析フレームワークVisionで顔認識を試した結果](https://dev.classmethod.jp/articles/ios-11-vision/)

## 注意

- このアプリは、iOS 15.0 以降で動作することを前提としています。
- ブラー処理の適用条件は、顔の向きと時間経過に基づいて決定されるため、顔の向きや時間経過によってブラー処理が適用されるかどうかが変化します。

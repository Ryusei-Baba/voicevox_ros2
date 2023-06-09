# voicevox_ros2

## ビルド・実行

```bash
git clone https://github.com/Ryusei-Baba/voicevox_ros2.git
cd voicevox_ros2
rosdep install -yi --from-paths .
cd ~/ws/
colcon build --symlink-install
source ~/ws/install/setup.bash
cd ~/ws/src/voicevox_ros2/
ros2 run voicevox_ros2 voicevox_ros2 --ros-args --params-file ./param/test_param.yaml
```
```
source ~/ws/install/setup.bash
ros2 topic pub --once /voicevox_ros2  voicevox_ros2_msgs/msg/Talk "{speaker_id: 1, text: "こんにちは、僕の名前はずんだもんなのだ"}"
```
適当なワークスペースに入れて、rosdepからのcolcon buildで動きます。

## パラメータ設定

こんなかんじにいじれます。
```
voicevox_ros2/param/test_param.yaml
```
```yaml
voicevox_ros2_node:
  ros__parameters:
    cpu_num_threads: 1
    load_models: [3, 8]
```

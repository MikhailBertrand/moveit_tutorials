Pick and Place
==============

MoveItでは，MoveGraspインターフェースを用いて把持が実行されます．物体を把持するためには，把持操作に含まれる様々な位置や姿勢を定義することを可能とする``moveit_msgs::Grasp`` msgを作成する必要があります．
このチュートリアルの出力は以下の動画のようなものとなります．:

.. raw:: html

    <div style="position: relative; padding-bottom: 5%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
        <iframe width="700px" height="400px" src="https://www.youtube.com/embed/QBJPxx_63Bs?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>

はじめに
---------------
もしまだ済ましていなければ，まず `はじめに <../getting_started/getting_started.html>`_ から始めてください.

デモの実行
----------------
ターミナルを２つ開き，1つ目のシェルでRVizを立ち上げ，全てが立ち上がるまで待ちます．: ::

    roslaunch panda_moveit_config demo.launch

2つ目のターミナルでは，pick and placeのチュートリアルを実行します．: ::

    rosrun moveit_tutorials pick_place_tutorial

このチュートリアル冒頭の動画のような出力が得られるはずです．

``moveit_msgs::Grasp``の理解
------------------------------------
ドキュメント全体は`こちら moveit_msgs/Grasp.msg. <http://docs.ros.org/melodic/api/moveit_msgs/html/msg/Grasp.html>`_

関連するmessage群：

* ``trajectory_msgs/JointTrajectory pre_grasp_posture`` - 把持実行前のend effector group内のジョイントの軌道位置を定義
* ``trajectory_msgs/JointTrajectory grasp_posture`` - 物体を把持するためのend effector group内のジョイントの軌道位置を定義
* ``geometry_msgs/PoseStamped grasp_pose`` - 把持を実行する際のエンドエフェクタの位置姿勢
* ``moveit_msgs/GripperTranslation pre_grasp_approach`` - 物体に近づくときの方向と移動距離を定義
* ``moveit_msgs/GripperTranslation post_grasp_retreat`` - 物体を把持した後に動く方向と移動距離を定義
* ``moveit_msgs/GripperTranslation post_place_retreat`` - 物体をある位置に置いた後に移動する向きと移動距離を定義

The Entire Code
---------------
The entire code can be seen :codedir:`here <pick_place>` in the moveit_tutorials GitHub project.

コード全容
---------------
コード全体は moveit_tutorials のGitHubリポジトリ内の:codedir:`こちら<pick_place>`から確認出来ます．

.. |br| raw:: html

   <br />

.. tutorial-formatter:: ./src/pick_place_tutorial.cpp

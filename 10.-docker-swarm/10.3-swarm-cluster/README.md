# 10.3 Swarm Cluster

머신 설정이 완료되었기에 Swarm 설정을 진행 할 수 있습니다.

제일 처음에 해야 할 일은 Swarm을 초기화하는 것입니다. 우리는 manager1 머신에 SSH를 설치하고 초기화합니다. manager1에 접속한 상태에서 아래의 명령어를 입력합니다. \(우리는 이미 이전에 manager1의 IP를 알아두었습니다.\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><code>docker@manager1:~$ docker swarm init --advertise-addr 192.168.99.100</code>
        </p>
        <p><code>Swarm initialized: current node (yli8mapw893qwmavhq7at3x0t) is now a manager.</code>
        </p>
        <p><code>To add a worker to this swarm, run the following command:</code>
        </p>
        <p>&lt;code&gt;&lt;/code&gt;</p>
        <p><code>    docker swarm join --token SWMTKN-1-0mlmww1rp83ji0tsonyzud0ny99tcymc3yyi3fx6ot7sydabtm-1iwjz0h9pxg4acro0sjm119q4 192.168.99.100:2377</code>
        </p>
        <p>&lt;code&gt;&lt;/code&gt;</p>
        <p><code>To add a manager to this swarm, run &apos;docker swarm join-token manager&apos; and follow the instructions.</code>
        </p>
        <p>&lt;code&gt;&lt;/code&gt;</p>
        <p><code>docker@manager1:~$</code>
        </p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>위에 출력된 내용을 보면 다른 노드를 연결하려면 docker swarm join 명령을 사용하라고 언급되어 있습니다. 노드는 작업자\(Worker\) 또는 관리자\(Leader\)로 참여할 수 있습니다. 어느 시점 에서든 하나의 Leader만 존재하고 다른 LEAD 노드는 현재 Leader가 아웃될 경우에 백업으로 사용됩니다.

아래의 명령어를 실행하여 Swarm 상태를 확인할 수 있습니다.

| `docker@manager1:~$ docker node ls ID                            HOSTNAME STATUS           AVAILABILITY MANAGER STATUS ENGINE VERSION yli8mapw893qwmavhq7at3x0t *   manager1 Ready           Active Leader 19.03.5 docker@manager1:~$` |
| :--- |


현재까지 단일노드 manager1이 존재하며 MANAGER열에 Leader 값을 가진 것을 확인할 수 있습니다.  



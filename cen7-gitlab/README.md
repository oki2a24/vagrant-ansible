## GitLab 構築注意点
- VM の割当メモリが 512 MB の場合、`gitlab-ctl reconfigure` の時間が多くかかるのと、ウェブブラウザからのレスポンスが非常に遅いため、1 GB 割り当てている。
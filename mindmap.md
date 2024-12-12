- JAM
  - $\mathbf{B}$ Block
    - $\mathbf{H}$ Header
      - $\mathbf{H}_p$: parent hash
        - $\mathbf{H}_p \in \mathbb{H} \,,\quad \mathbf{H}_p \equiv
          \mathcal{H}(\mathcal{E}(P(\mathbb{H})))$
      - $\mathbf{H}_r$: prior state root
        - $\mathbf{H}_r \equiv \mathcal{M}_\sigma(\sigma)$
          $\sigma$ (state)
          - $\alpha$: Authorisation pool
          - $\beta$: recent history blocks ($\mathbf{H} = 8$)
            - $h$: header hash
            - $\mathbf{b}$: a output of MMR append function $\mathcal{A}$
              (Appendix E.2)
            - $s$: state root
            - $\mathbf{p}$: a dictionary of work packages mapping to work
              reports
          - $\gamma$: safrole basic states
            - $\gamma_\mathbf{k}$: validator key set for next epoch
            - $\gamma_z$: ring root
            - $\gamma_\mathbf{s}$: slot-sealer series
            - $\gamma_\mathbf{a}$: tickets accumulator determine the tickets used for next epoch
          - $\delta$: service accounts
            - $\delta \in \mathbb{D} \langle \mathbb{N}_S \to \mathbb{A} \rangle$
              $\mathbb{A}$: service account
              - $\mathbf{s}$: storage dictionary
              - $\mathbf{p}$: preimage dictionary
              - $\mathbf{l}$: preimage history
              - $b$: balance
              - $c$: code hash
              - $g$: `Accumulate` gas
              - $m$: `On Transfer` gas
              - $\Lambda$: ==historical lookups function==
          - $\eta$: entropy accumulator
          - $\iota$: duplicate of $\gamma_{r}$ at beginning of epoch
          - $\kappa$: current epoch active validator set
          - $\lambda$: last epoch active validator set
          - $\rho$: intermediate state
          - $\tau$: The most recent block's $\tau$imeslot.
          - $\varphi$: Authorisation Queue (used to update $\alpha$)
          - $\chi$: service privileges
            - $\chi_m$: a manager service
            - $\chi_a$: a service who can alter $\varphi$
            - $\chi_v$: a service who can alter $\iota$
            - $\chi_g$: a gas dictionary
          - $\psi$: disputes state
            - $\psi_\mathbf{g}$: good
            - $\psi_\mathbf{b}$: bad
            - $\psi_\mathbf{w}$: wonky
            - $\psi_\mathbf{o}$: offenders
          - $\pi$: validator activity statistics
            - $
                \pi \in \llbracket{\llbracket{(b \in \mathbb{N} \ , t \in \mathbb{N} \ , p \in \mathbb{N} \ , d \in \mathbb{N} \ , g \in \mathbb{N} \ , a \in \mathbb{N} )\rrbracket_\mathsf{V} \rrbracket_2}}
              $
              - $b$: The number of blocks produced by the validator
                - $\pi^{\prime}_0[v]_b \equiv \mathbf{a}[v]_b + (v = \mathbf{H}_i)$
              - $t$: The number of tickets introduced by the validator
                - $
                    \pi^{\prime}_0[v]_t \equiv \mathbf{a}[v]_t + 
                    \begin{cases}
                      |\mathbf{E}_T| &\text{if } v = \mathbf{H}_i \\
                      0 &otherwise
                    \end{cases}
                  $
              - $p$: The number of preimages introduced by the validator
                - $
                    \pi^{\prime}_0[v]_p \equiv \mathbf{a}[v]_p + 
                    \begin{cases}
                      |\mathbf{E}_P| &\text{if } v = \mathbf{H}_i \\
                      0 &otherwise
                    \end{cases}
                  $
              - $d$: The total number of octets across all preimages introduced by the validator
                - $
                    \pi^{\prime}_0[v]_d \equiv \mathbf{a}[v]_d + 
                    \begin{cases}
                     \sum_{d \in \mathbf{E}_P}|d| &\text{if } v = \mathbf{H}_i \\
                      0 &otherwise
                    \end{cases}
                  $
              - $g$: The number of reports guaranteed by the validator
                - $\pi^{\prime}_0[v]_g \equiv \mathbf{a}[v]_g + (\kappa'_v \in \mathbf{R})$
              - $a$: The number of availability assurances by the validator
                - $\pi^{\prime}_0[v]_a \equiv \mathbf{a}[v]_a + (\exists a \in \mathbf{E}_A : a_v = v)$
            - $(\mathbf{a}, \pi^{\prime}_1) 
                \equiv 
                \begin{cases}
                (\pi_0, \pi_1) & \quad \text{if } e' = e \\
                ([(0,...,[0,...]),...], \pi_0) & \quad \text{otherwise}
                \end{cases}$
              - $e = \lfloor \frac {\tau}{\mathsf{E}} \rfloor$
              - $e' = \lfloor \frac{\tau'}{\mathsf{E}} \rfloor$
          - $\vartheta$
          - $\xi$
      - $\mathbf{H}_x$: extrinsic hash
      - $\mathbf{H}_t$: a time slot index
      - $\mathbf{H}_e$: the epoch
      - $\mathbf{H}_w$: winning tickets
      - $\mathbf{H}_o$: offenders markders
        - keys $k$ belongs to culprits and faults
      - $\mathbf{H}_i$: a Bandersnatch block author index
      - $\mathbf{H}_v$: the entropy-rielding VRF signatrue
      - $\mathbf{H}_s$: a block seal
    - $\mathbf{E}$ Extrinsic
      - $\mathbf{E}_T$: tickets
        - $r$: ticket entry index
        - $p$: ringVRF proof
      - $\mathbf{E}_D$: disputes
        - $\mathbf{v}$: verdicts
        - $\mathbf{c}$: culprits
        - $\mathbf{f}$: faults
      - $\mathbf{E}_P$: preimages
        - $\mathbf{E}_P \in \llbracket (\mathbb{N}_S, \mathbb{Y}) \rrbracket$
          - $\mathbb{N}_S$: service index
          - $\mathbb{Y}$: preimage (blob string)
      - $\mathbf{E}_A$: availability (assurances)
        - $a$: anchor
        - $f$: bitstring
        - $v$: validator index
        - $s$: signature
      - $\mathbf{E}_G$: guarantees

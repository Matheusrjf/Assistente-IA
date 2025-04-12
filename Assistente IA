package com.assistente.virtual;

import org.springframework.web.bind.annotation.*;
import org.springframework.web.client.RestTemplate;
import org.springframework.http.ResponseEntity;
import org.springframework.http.HttpEntity;
import org.springframework.http.HttpHeaders;
import org.springframework.http.HttpMethod;

@RestController
@RequestMapping("/assistente")
public class AssistenteController {

    private static final String OPENAI_API_URL = "https://api.openai.com/v1/completions";
    private static final String OPENAI_API_KEY = "SUA_CHAVE_OPENAI"; // Substitua pela sua chave

    @PostMapping("/perguntar")
    public String perguntar(@RequestBody String pergunta) {
        RestTemplate restTemplate = new RestTemplate();
        HttpHeaders headers = new HttpHeaders();
        headers.set("Authorization", "Bearer " + OPENAI_API_KEY);
        headers.set("Content-Type", "application/json");
        
        String requestBody = "{"model":"text-davinci-003", "prompt":""" + pergunta + """, "max_tokens":150}";
        HttpEntity<String> entity = new HttpEntity<>(requestBody, headers);
        
        ResponseEntity<String> response = restTemplate.exchange(OPENAI_API_URL, HttpMethod.POST, entity, String.class);
        return response.getBody();
    }
}
